# customfly
<?php
namespace fly\MyPlugin;

use pocketmine\plugin\PluginBase;

class MyPlugin extends PluginBase{

    public function onEnable(){
        $this->getLogger()->info("onEnable() fly has been enabled");
    }

    public function onDisable(){
        $this->getLogger()->info("onDisable() fly has been disabled");
    }
}public function onCommand(CommandSender $sender, Command $command, $label, array $args){
    if(strtolower($command->getName()) === "fly"){
        // Execute logic
        return true;
    }

    return false;
}
public function onCommand(CommandSender $sender, Command $cmd, $label, array $args) 
     { 
        if (strtolower($cmd->getName()) == "fly") { 
             if ($sender->hasPermission("cfly.command.fly")) { 
                 if ($sender instanceof Player) { 
                     if ($this->isPlayer($sender)) { 
                         $this->removePlayer($sender); 
                         $sender->setAllowFlight(false); 
                         $sender->sendMessage(TextFormat::RED . "You have disabled fly mode!"); 
                         return true; 
                     } else { 
                         $this->addPlayer($sender); 
                         $sender->setAllowFlight(true); 
                         $sender->sendMessage(TextFormat::RED . "You have enabled fly mode!"); 
                         return true; 

