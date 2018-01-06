# Introducing-Collections (觀念上的講解)

## 在哪裡可以使用Collection

- 使用 Laravel Framework 開發，內帶 Collection 類
- 可以單獨使用 Composer 安裝 (不一定要用Laravel，你也可以在純PHP中，使用composer安裝，用colllection來refactor原本大量for, array的寫法)
- 如果有記憶體考量，就不適合，這邊這種寫法是注重可讀性、可維護性
```
Composer require Illuminate/Support
```
- Collection API
Https://laravel.com/api/5.1/Illuminate/Support/Collection.html

```php
function getUserEmails($users)
{
    return (new Collection($users))->filter(function ($user) {
        return $user->email !== null;
    })->map(function ($user) {
        return $user->email;
    })->toArray();
}
```

## 把握一些原則

- 熟悉collection的function，在操作的時候盡量就不用大量foreach和array，可以參考下面的function name，查API的使用方法
Pipeline programming is about operating at a higher level of abstraction. Instead of
doing things with the items in a collection, you do things to the collection itself.

- Map it, filter it, reduce it, sum it, zip it, reverse it, transpose it, flatten it, group it, count
it, chunk it, sort it, slice it, search it; if you can do it with a foreach loop, you can do it
with a collection method.

