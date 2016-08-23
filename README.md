# customfly
<?php
namespace ExampleAuthor\MyPlugin;

use pocketmine\plugin\PluginBase;

class MyPlugin extends PluginBase{

    public function onEnable(){
        $this->getLogger()->info("onEnable() has been called!");
    }

    public function onDisable(){
        $this->getLogger()->info("onDisable() has been called!");
    }
}
