# TripSorter

## Task
You are given a stack of boarding cards for various transportations that will take
you from a point A to point B via several stops on the way. All of the boarding
cards are out of order and you don't know where your journey starts, nor where it
ends. Each boarding card contains information about seat assignment, and means
of transportation (such as flight number, bus number etc).
Write an API that lets you sort this kind of list and present back a description of
how to complete your journey.
For instance the API should be able to take an unordered set of boarding cards,
provided in a format defined by you, and produce this list:
1. Take train 78A from Madrid to Barcelona. Sit in seat 45B.
2. Take the airport bus from Barcelona to Gerona Airport. No seat assignment.
3. From Gerona Airport, take flight SK455 to Stockholm. Gate 45B, seat 3A.
Baggage drop at ticket counter 344.
4. From Stockholm, take flight SK22 to New York JFK. Gate 22, seat 7B.
Baggage will we automatically transferred from your last leg.
5. You have arrived at your final destination.
The list should be defined in a format that's compatible with the input format.
The API is to be an internal PHP API so it will only communicate with other parts of
a PHP application, not server to server, nor server to client. Use PHP-doc to
document the input and output your API accepts / returns.
## Installation
From the root directory of the file, run these commands from command line:
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
```
once you've done this, run command:
```bash
php composer.phar installer
```
then unlink composer-setup.php with:
```bash
php -r "unlink('composer-setup.php');"
```
## Run Tests
Run phpunit command from root directory of the project.
```bash
phpunit
```

## Run Code
```bash
$tripSorter = new TripSorter();
$sortedBoardingCards = $tripSorter->addBoardingCard($airplaneCard1)
    ->addBoardingCard($airplaneCard2)
    ->addBoardingCard($busCard)
    ->addBoardingCard($trainCard)
    ->sortBoardingCards()
    ->getSortedBoardingCards();
```
