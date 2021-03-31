# POO----Basics-Part-1-Faire-ses-premi-res-classes

<?php
// index.php

require_once 'Bicycle.php';
$bike = new Bicycle("red", 15);

// Moving rockrider
echo $bike->forward();
echo '<br> Vitesse du vélo : ' . $bike->getCurrentSpeed() . ' km/h' . '<br>';
echo $bike->brake();
echo '<br> Vitesse du vélo : ' . $bike->getCurrentSpeed() . ' km/h' . '<br>';
echo $bike->brake() . '<br>';

// Instanciation d'un nouvel objet $rockrider avec couleur et vitesse
$rockrider = new Bicycle("green",10);

// Moving rockrider
echo $rockrider->forward();
echo '<br> Vitesse du vélo : ' . $rockrider->getCurrentSpeed() . ' km/h' . '<br>';
echo $rockrider->brake();
echo '<br> Vitesse du vélo : ' . $rockrider->getCurrentSpeed() . ' km/h' . '<br>';
echo $rockrider->brake(). '<br>';

//Instanciation de l'objet $tornado
$tornado = new Bicycle( "black", 8);

//Moving tornado
echo $tornado->forward();
echo '<br> Vitesse du vélo : ' . $tornado->getCurrentSpeed() . ' km/h' . '<br>';
echo $tornado->brake();
echo '<br> Vitesse du vélo : ' . $tornado->getCurrentSpeed() . ' km/h' . '<br>';
echo $tornado->brake(). '<br>';


/////// CARS ///////
require_once 'Cars.php';

//Instanciation de l'objet $mini
$mini = new Cars("red", 5, "electric");
// Moving mini
echo $mini->start();
echo '<br> Démarrage ok' . '<br>';
echo $mini->forward();
echo '<br> Vitesse de la voiture : ' . $mini->getCurrentSpeed() . ' km/h' . '<br>';
echo $mini->brake();
echo '<br> Vitesse de la voiture : ' . $mini->getCurrentSpeed() . ' km/h' . '<br>';
echo $mini->brake();


<?php

// Bicycle.php

class Bicycle
{
    private $color;
    private $currentSpeed;
    private $nbSeats = 1;
    private $nbWheels = 2;

    public function forward()
    {
        $this->currentSpeed;
        return "Go !";
    }

    public function brake(): string 
    {
        $sentence = "";
        while ($this->currentSpeed > 0) {
        $this->currentSpeed--;
        $sentence .= "Brake !!!";
    }
        $sentence .= "I'm stopped !";
        return $sentence;
    }


    public function getColor(): string 
    {
        return $this->color;
    }
    public function setColor(string $color): void 
    {
        $this->color = $color;
    }

    public function __construct(string $color, int $currentSpeed)
    {
        $this->color = $color;
        $this->currentSpeed = $currentSpeed;
    }

    public function getCurrentSpeed(): int 
    {
        return $this->currentSpeed;
    }
     public function setCurrentSpeed(int $currentSpeed): void 
     {
         if($currentSpeed >= 0){
             $this->currentSpeed = $currentSpeed;
         }
     }
} 



<?php

class Cars
{
    private $color;
    private $currentSpeed;
    private $nbSeats;
    private $nbWHeels;
    private $energy;
    private $energyLevel;

    public function __construct(string $color, int $nbSeats,string $energy)
    {
        $this->color = $color;
        $this->nbSeats = $nbSeats;
        $this->energy = $energy;
    }
     public function forward()
     {
         $this->currentSpeed;
         return "Go !";
     }

     public function brake(): string 
     {
         $sentence = "";
         while ($this->currentSpeed > 0){
             $this->currentSpeed--;
             $sentence .= "Brake !!!";
         }
         $sentence .= "I'm stopped !";
         return $sentence;
     }
     public function start(){
         $this->currentSpeed = 20;
     }
     public function getNbWheels(): int 
     {
         return $this->NbWheels;
     }

     public function getCurrentSpeed(): int 
     {
         return $this->currentSpeed;
     }
      public function getColor(): string 
      {
          return $this->color;
      }
      public function getNbSeats(): string 
      {
          return $this->nbSeats;
      }
      public function getEnergy(): string 
      {
          return $this->energy;
      }
      public function getEnergyLevel(): string 
      {
          return $this->energyLevel;
      }
}
    
