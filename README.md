# Validasi API PHP Native

```php
// cek get key
if (empty($_GET)) {
  // cek header key
  if (empty($_SERVER['HTTP_KEY'])) {
    die(json_encode(["status" => "eror", "message" => "Key empty"]));
  } else {
    $headerStringValue = $_SERVER['HTTP_KEY'];

    if ($headerStringValue != $apiKey) {
      die(json_encode(["status" => "eror", "message" => "API Key wrong"]));
    }
  }
} else {
  if (empty($_GET["key"])) {
    die(json_encode(["status" => "eror", "message" => "Key empty"]));
  }

  if ($_GET["key"] != $apiKey) {
    die(json_encode(["status" => "eror", "message" => "API Key wrong"]));
  }
}

