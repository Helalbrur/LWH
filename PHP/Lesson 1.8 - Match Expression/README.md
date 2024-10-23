# Match expression syntax is one of the nicest features in PHP 8 that improves the switch syntax in multiple ways.
```php
$request_method = "post";
$status = match($request_method) {
    'post' => $this->handlePost(),
    'get', 'head' =>  $this->handleGet(),
    default => throw new \Exception('Unsupported'),
};

 switch ($request_method)
 {
   case 'post':
       $status = $this->handlePost();
       break;
   case 'get':
   case 'head':
       $status = $this->handleGet();
       break;
   default:
       throw new \Exception('Unsupported'); 
 }

```