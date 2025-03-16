# Parent Class: Smartphone
class Smartphone:
    def __init__(self, brand, model, storage, battery):
        self.brand = brand
        self.model = model
        self.storage = storage  # Public Attribute
        self.__battery = battery  # Private Attribute (Encapsulated)

    def display_info(self):
        print(f"📱 {self.brand} {self.model} - {self.storage}GB Storage")

    def charge_battery(self, percentage):
        if 0 <= percentage <= 100:
            self.__battery = percentage
            print(f"🔋 Battery charged to {self.__battery}%")
        else:
            print("❌ Invalid battery percentage!")

    def get_battery(self):  # Getter method for the private attribute
        return f"🔋 Battery Level: {self.__battery}%"

# Child Class: GamingPhone (inherits from Smartphone)
class GamingPhone(Smartphone):
    def __init__(self, brand, model, storage, battery, refresh_rate):
        super().__init__(brand, model, storage, battery)  # Call parent constructor
        self.refresh_rate = refresh_rate  # Additional attribute for gaming phones

    # Overriding the display_info() method (Polymorphism)
    def display_info(self):
        print(f"🎮 {self.brand} {self.model} - {self.storage}GB | {self.refresh_rate}Hz Display")

# Creating an instance of Smartphone
phone1 = Smartphone("Samsung", "Galaxy S23", 256, 80)
phone1.display_info()
print(phone1.get_battery())  # Access private attribute via getter method

# Creating an instance of GamingPhone
gaming_phone = GamingPhone("Asus", "ROG Phone 7", 512, 90, 165)
gaming_phone.display_info()  # Overridden method
gaming_phone.charge_battery(100)
# OOP-Assignment
