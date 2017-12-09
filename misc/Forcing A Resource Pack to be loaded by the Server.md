# Forcing A Resource Pack to be loaded by the Server
#### Language: PHP<br />API: PocketMine-MP API 3.0.0-ALPHA9/10

### Code:
```php
/**
 * Forces a ResourcePack to be loaded by PocketMine
 *
 * Attribution:
 *  - Main::forceResourcePack() is from Ad5001's "Spooky" plugin
 *  - URL: https://github.com/Ad5001/Spooky/blob/master/src/Ad5001/Spooky/Main.php#L57-L73 (as of December 8, 2017)
 *
 *
 * @param string $path
 */
private function forceResourcePack(string $path){
    $pack = new ZippedResourcePack($path);
    $r = new \ReflectionClass("pocketmine\\resourcepacks\\ResourcePackManager");
    $resourcePacks = $r->getProperty("resourcePacks");
    $resourcePacks->setAccessible(true);
    $rps = $resourcePacks->getValue($this->getServer()->getResourceManager());
    $rps[] = $pack;
    $resourcePacks->setValue($this->getServer()->getResourceManager(), $rps);
    $resourceUuids = $r->getProperty("uuidList");
    $resourceUuids->setAccessible(true);
    $uuids = $resourceUuids->getValue($this->getServer()->getResourceManager());
    $uuids[$pack->getPackId()] = $pack;
    $resourceUuids->setValue($this->getServer()->getResourceManager(), $uuids);
    $forceResources = $r->getProperty("serverForceResources");
    $forceResources->setAccessible(true);
    $forceResources->setValue($this->getServer()->getResourceManager(), true);
}
```
### Credits:
 - Main::forceResourcePack() is from Ad5001's "Spooky" plugin
 - URL: https://github.com/Ad5001/Spooky/blob/master/src/Ad5001/Spooky/Main.php#L57-L73 (as of December 8, 2017)
### Example Usage:
```php
$this->forceResourcePack($this->getDataFolder() . "resources.mcpack");
```
