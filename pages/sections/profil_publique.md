---
layout: section
title: Rendre un profil publique aux autres utilisateurs
level: 2
---
# Rendre un profil publique aux autres utilisateurs

---
hideInToc: true
---

src/Sylius/Bundle/ApiBundle/DataProvider/CustomerItemDataProvider.php
```php
final class CustomerItemDataProvider implements RestrictedDataProviderInterface, ItemDataProviderInterface
{
    public function getItem(string $resourceClass, $id, string $operationName = null, array $context = [])
    {
        /** @var ShopUserInterface|null $user */
        $user = $this->userContext->getUser();

        if ($user instanceof AdminUserInterface && in_array('ROLE_API_ACCESS', $user->getRoles(), true)) {
            return $this->customerRepository->find($id);
        }

        if (
            $user instanceof ShopUserInterface && $id === $user->getCustomer()->getId()
        ) {
            return $this->customerRepository->find($id);
        }

        if ($user === null && $operationName === 'shop_verify_customer_account') {
            return $this->customerRepository->find($id);
        }

        return null;
    }

    public function supports(string $resourceClass, string $operationName = null, array $context = []): bool
    {
        return is_a($resourceClass, CustomerInterface::class, true);
    }
}
```
---
hideInToc: true
---

src/Sylius/Bundle/ApiBundle/DataProvider/CustomerItemDataProvider.php
```diff
final class CustomerItemDataProvider implements RestrictedDataProviderInterface, ItemDataProviderInterface
{
    public function getItem(string $resourceClass, $id, string $operationName = null, array $context = [])
    {
-        /** @var ShopUserInterface|null $user */
-        $user = $this->userContext->getUser();

-        if ($user instanceof AdminUserInterface && in_array('ROLE_API_ACCESS', $user->getRoles(), true)) {
-            return $this->customerRepository->find($id);
-        }

-        if (
-            $user instanceof ShopUserInterface && $id === $user->getCustomer()->getId()
-        ) {
-            return $this->customerRepository->find($id);
-        }

-        if ($user === null && $operationName === 'shop_verify_customer_account') {
-            return $this->customerRepository->find($id);
-        }

-        return null;
        return $this->customerRepository->find($id);
    }

    public function supports(string $resourceClass, string $operationName = null, array $context = []): bool
    {
        return is_a($resourceClass, CustomerInterface::class, true);
    }
}
```