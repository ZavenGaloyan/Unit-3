# Code
```py
class Vehicle:
    '''Class for vehicle and parent class for electric vehicle.'''
    #attributes
    def __init__(self, brand:str, model:str, type:str):
        self.brand = brand
        self.model = model
        self.type = type
        self.gas_tank_size = 14
        self.fuel_level = 0
        '''Set original fuel level and tank size'''
    #methods
    def fuel_up(self):
        self.fuel_level = self.gas_tank_size
        return 'Gas tank is now full.'
    def drive(self):
        '''Give the user the message that the vehicle(tell with model) is driving'''
        return f'The {self.model} is now driving.'
class electric_vehicles(Vehicle):
    '''child class of Vehicle'''
    #attributes
    def __init__(self,brand, model, type, distance:int):
        super().__init__(brand, model,type)
        '''use super to inherit attributes from parent class'''
        self.battery = Battery()
        '''Set battery = battery size from battery class'''
        self.distance = distance
    #method
    def charge_car(self, new_value):
        '''Charge the car to the new value'''
        self.battery.charge_bat(new_value)
        '''Tell the user that the battery is charged'''
        return f"The current battery is at {self.battery}kwh"
    def drive(self):
        '''Method returns the total distance driven and notify that the vehicla starts to drive. It's overwriting the drive method in parent class'''
        return f"The distance so far is {self.distance} km. The {self.model} is driving."
class Battery:
    '''A class to represent a battery bank. By  default its size is 20 kwh'''
    #attributes
    def __init__(self,size:int = 20):
        self.size = size
        self.charge_level = 0
    #methods
    def get_charge(self):
        '''This method returns the current charge level'''
        return self.charge_level
    def get_range(self):
        '''This method returns an estimate of the km that the car can drive'''
        return 10*self.charge_level
    def charge_bat(self,new_value:int):
        '''Charge the charge level to the new value'''
        self.charge_level = new_value

    def __repr__(self):
        return f"<Battery> size {self.size} charge {self.charge_level}"

my_tesla = electric_vehicles ('Tesla', "model 3", 'car', 4000)
print(my_tesla.battery.get_charge())
my_tesla.charge_car(50)
print(my_tesla.battery.get_charge())
my_tesla.battery.charge_bat(60)

print(my_tesla.battery.get_charge())

#create a battery
replacement_bat = Battery()
print(replacement_bat.get_charge())
import random
Stock_bats = []
'''Create list for battery stock'''
for i in range(100):
    '''Create different size battery and put in the list called Stock_bats'''
    a_battery = Battery(size=random.randint(10,100))
    Stock_bats.append(a_battery)
    print(a_battery)

#Using python lists and for
for bat in Stock_bats:
    '''Charge all the battery to 60 and show the charge of each battery in the stock'''
    bat.charge_bat(50)
    print(bat)

#Using traditional indexing
for i in range(100):
    '''Charge all the battery to 50 and show the charge of each battery in the stock'''
    Stock_bats[i].charge_bat(50)
    print(Stock_bats[i])
 ```
 
 
 # Outcome
 <img width="1440" alt="Quiz33" src="https://user-images.githubusercontent.com/82266864/154171628-a6f7ef08-dfca-441b-b953-97e46e4d8fa1.png">
