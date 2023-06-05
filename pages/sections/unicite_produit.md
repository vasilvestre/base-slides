---
layout: section
title: Il n'y a qu'un variant produit
level: 2
---
# Tout les produits sont uniques

---
hideInToc: true
---

src/Sylius/Bundle/ApiBundle/Serializer/ProductNormalizer.php
```diff
final class ProductNormalizer implements ContextAwareNormalizerInterface, NormalizerAwareInterface
{
    public function normalize($object, $format = null, array $context = [])
    {
        Assert::isInstanceOf($object, ProductInterface::class);
        Assert::keyNotExists($context, self::ALREADY_CALLED);

        $context[self::ALREADY_CALLED] = true;

        $data = $this->normalizer->normalize($object, $format, $context);

-        $data['variants'] = $object
-            ->getEnabledVariants()
-            ->map(fn (ProductVariantInterface $variant): string => $this->iriConverter->getIriFromItem($variant))
-            ->getValues()
-        ;
+        unset($data['variants']);

        $defaultVariant = $this->defaultProductVariantResolver->getVariant($object);
-        $data['defaultVariant'] = $defaultVariant === null ? null : $this->iriConverter->getIriFromItem($defaultVariant);
+        $data['defaultVariant'] = $defaultVariant === null ? null : $this->normalizer->normalize($defaultVariant, $format, $context);

        return $data;
    }
}
```