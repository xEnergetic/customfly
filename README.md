customfly
<?php
namespace fly\MyPlugin;

use pocketmine\plugin\PluginBase;
use pocketmine\plugin\PluginBase; 
5 use pocketmine\event\Listener; 
6 use pocketmine\utils\TextFormat; 
7 use pocketmine\event\entity\EntityDamageEvent; 
8 use pocketmine\event\entity\EntityDamageByEntityEvent; 
9 use pocketmine\Player; 
10 use pocketmine\command\Command; 
11 use pocketmine\command\CommandSender; 
12  




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

