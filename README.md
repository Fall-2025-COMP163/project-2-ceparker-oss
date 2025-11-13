[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/mMxhKicI)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21518234&assignment_repo_type=AssignmentRepo)
# COMP 163 - Project 2: Character Abilities Showcase

## 🎯 Project Overview

Build a simple character system that demonstrates mastery of object-oriented programming fundamentals: inheritance, method overriding, polymorphism, and composition. This project focuses on core OOP concepts without the complexity of a full game system.

## 📋 Getting Started

1. **Complete your implementation** in `project2_starter.py`
2. **Test your code** by running: `python project2_starter.py`
3. **Run automated tests** with: `python -m pytest tests/ -v`
4. **Commit and push** to see GitHub test results

## 🏗️ What You're Building

### **Class Structure (6 Classes Total)**

```
Character (base class)
    ↓
Player (inherits from Character)  
    ↓
Warrior, Mage, Rogue (inherit from Player)

Weapon (composition - separate class)
```

### **Required Stats for Each Class:**

| Class   | Health | Strength | Magic | Special Ability |
|---------|--------|----------|-------|-----------------|
| Warrior | 120    | 15       | 5     | Power Strike    |
| Mage    | 80     | 8        | 20    | Fireball        |
| Rogue   | 90     | 12       | 10    | Sneak Attack    |

## 🎮 Core Functionality

### **All Characters Must Have:**
- `attack(target)` - Basic attack method
- `take_damage(damage)` - Reduce health
- `display_stats()` - Print character information

### **Players Additionally Have:**
- `character_class` attribute (like "Warrior", "Mage")
- `level` and `experience` attributes
- Enhanced `display_stats()` that shows player info

### **Special Abilities (Each Class):**
- **Warrior**: `power_strike(target)` - High damage attack
- **Mage**: `fireball(target)` - Magic damage attack
- **Rogue**: `sneak_attack(target)` - Critical hit attack

### **Weapons (Composition):**
- `Weapon(name, damage_bonus)` - Characters can HAVE weapons
- `display_info()` - Show weapon information

## ✅ Testing Your Code

### **Local Testing**
```bash
# Run all tests
python -m pytest tests/ -v

# Run specific test categories
python -m pytest tests/test_inheritance.py -v
python -m pytest tests/test_method_overriding.py -v
python -m pytest tests/test_special_abilities.py -v

# Test your main program
python project2_starter.py
```

### **GitHub Testing**

After pushing your code, check the **Actions** tab to see automated test results:

- ✅ **Inheritance Tests** (20 points) - Class structure and inheritance chain
- ✅ **Method Overriding Tests** (20 points) - Polymorphism and customized methods
- ✅ **Special Abilities Tests** (15 points) - Character abilities and composition

## 🎮 Example Usage

Your program should work like this:

```python
# Create characters (inheritance)
warrior = Warrior("Marcus")
mage = Mage("Aria")  
rogue = Rogue("Shadow")

# Polymorphism - same method, different behavior
for character in [warrior, mage, rogue]:
    character.attack(target)  # Each attacks differently

# Special abilities
warrior.power_strike(enemy)
mage.fireball(enemy)
rogue.sneak_attack(enemy)

# Composition
sword = Weapon("Iron Sword", 15)
sword.display_info()

# Test battle system (provided for you)
battle = SimpleBattle(warrior, mage)
battle.fight()
```

## 🎲 SimpleBattle System (Provided)

You have a **SimpleBattle** class already written that you can use to test your characters:

```python
battle = SimpleBattle(character1, character2)
battle.fight()  # Simulates a simple battle
```

**⚠️ DO NOT MODIFY the SimpleBattle class** - it's provided for testing your implementations.

## ⚠️ Important Notes

### **Protected Files**
- **DO NOT MODIFY** files in the `tests/` directory
- **DO NOT MODIFY** the `SimpleBattle` class
- Modifying protected files will result in automatic academic integrity violation

### **AI Usage Policy**
- ✅ **Allowed**: AI assistance for implementation, debugging, learning
- 📝 **Required**: Document AI usage in code comments
- 🎯 **Must be able to explain**: Every class and method during interview

## 🏆 Grading

- **Inheritance Tests (20%)**: Proper 3-level inheritance chain
- **Method Overriding (20%)**: Polymorphism and customized behaviors
- **Special Abilities (15%)**: Character-specific methods and composition
- **Code Quality (5%)**: Professional comments and documentation
- **Interview (40%)**: Code explanation and live coding

## 🎨 Bonus Creative Elements

Feel free to add your own creative touches for bonus points:
- Additional character classes beyond the three required
- More weapon types with different properties
- Enhanced special abilities with unique effects

—----------------------------------Created Readme—-------------------------------------------
What Is This?:
Hello Again! This is a battle interface, as you can choose between three roles: Mage, Warrior, and Rogue, and battle between all three! All three have special moves to ensure victory, but who will come out on top?

AI/Bonus:
No AI or Bonus attributes were created or used for this project

How To Run:
It's simple: create a variable ex(warrior) and ​make it equal to one of the classes shown above! EX: Warrior= Warrior(“Sir Galihand”)

Now that you have a variable equal to your class, you can call certain actions
Actions:
display_stats: displays your character's strength, magic, etc.
Attack: allows you to attack other characters.
SPECIAL ATTACKS: power_strike,fireball,sneak_attack
			Warrior           Mage    Rogue 
You can also create a class for certain weapons; you can choose sats for them as well. EX: weapon(“Iron Sword”,10), you can display it using display_stats as well


How It Works:
In this project, six main classes do what's stated above, starting with the Character class. 
Character:
The character class is created to create the attributes that will be later used to determine factors for different characters. These attributes consist of (self.name, self.class, self.health, and self.magic). After, we can use attack, which is how the attributes are first used, as our damage is based on a character's strength at first, with the method take_damage, then being called to reduce a character's health based on the damage. Finally, we have display_stats, which will simply display all the named attributes previously stated. 
Player:
The player class is the derived class of Character, meaning that it will obtain ALL aspects from the Base class( Character in this sense). We first start by initializing this class, as it has a parameter that will correspond to the previous class when calling it 
(self, name,character_class, health, strength, magic). Since the previous attributes are created with the creation of this list, they are aligned with the said parameters (EX: self.health=health), with new attributes being created to perform the same task (EX: self. character_class=character_class). Display_stats is also created, but this opens an important rule, overriding, as naming methods with the same name will call the closest method named this, in this case Player. To display both, you must call the classes' display method individually (Player.display_info(self)). After this is called, the class prints the new information created (self.info and self. self.character_class).

Mage, Warrior, Rogue:
	
These classes are all derived classes under Player, as they all inherit Person's attributes and methods (meaning characters too). For these classes, they are initialized by calling the person _int_ method, corresponding to all the previous parameters, with arguments that correspond to each attribute.
EX: Player.__init__(self,name, "Mage", 80, 8, 20)
With all of them being called, you gain these inherited attributes, all of them correlating to these arguments (EX: self.name= ”Mage”). Now, for attacking, each class overrides the original attack method, recalculating the amount of damage based on different aspects, all still using take_damage to reduce the amount of damage that will be taken. Along with the attack, we have special moves with different attacks based on the character: power_strike, fireball, and sneak_attack. These will also reduce health exponentially, and are special based on the character itself, with the different moves being based on the character (EX: Mage has fireball). 
Weapon:
Finally, we have the weapon class. This class is simple, as it's used to store weapons, and it creates new attributes (the weapon name and damage bonus), which can then be displayed to show these new attributes using display_info.




