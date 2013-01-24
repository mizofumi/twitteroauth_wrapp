#なにこれ
twitteroauth.phpを使ったwrapperです。

##使い方
rest.phpをtwitteroauth.phpと同じディレクトリに入れて下さい。

##コード例
```php
require_once 'rest.php';  
$restapi = new TwitterAPI($consumer_key, $consumer_secret, $access_token, $access_token_secret);  

//Tweet
$status = 'TestTweet';
$restapi->UpdateStatus($status);

//Reply
$status = '@hogehoge TestReplyTweet';
$inReplyTo = '1234567890';
$restapi->UpdateStatus($status,$inReplyTo );

//GetHomeTimeline
$count = 200;
$sinceId = 123456789;
$maxId = 987654321;
$HomeTL = $restapi->GetHomeTimeline($count,$sinceId,$maxId);
```