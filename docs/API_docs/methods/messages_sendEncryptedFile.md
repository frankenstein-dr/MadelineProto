---
title: messages_sendEncryptedFile
---
## Method: messages\_sendEncryptedFile  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|peer|[InputEncryptedChat](../types/InputEncryptedChat.md) | Required|
|random\_id|[long](../types/long.md) | Required|
|data|[bytes](../types/bytes.md) | Required|
|file|[InputEncryptedFile](../types/InputEncryptedFile.md) | Required|


### Return type: [messages\_SentEncryptedMessage](../types/messages_SentEncryptedMessage.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) {
    $this->bot_login($token);
}
if (isset($number)) {
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$messages_SentEncryptedMessage = $MadelineProto->messages_sendEncryptedFile(['peer' => InputEncryptedChat, 'random_id' => long, 'data' => bytes, 'file' => InputEncryptedFile, ]);
```