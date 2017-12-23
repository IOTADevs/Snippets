# RepeatingAsyncTask
#### Language: PHP<br />API: PocketMine-MP API 1.0.0 - Later Versions

### Code: <sup>(Use this in your AsyncTask's onRun method)</sup>
```php
public function onRun(){
  while(true){
    // Do Async Stuff
    sleep(25); // Delay for 25 seconds
  }
}
```
### Note:
 - Using sleep() on the Main Thread basically freezes it and is a bad practice... But in this case, since we're running on another Asynchronous Thread, It wouldn't freeze the Main Thread and it's acceptable.
