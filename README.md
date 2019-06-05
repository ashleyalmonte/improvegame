# improvegame

All_UNITS = []

class Unit
  attr_accessor :name, :hp, :mp, :atk, :magic, :status, :speed, :ct , :maxhp, :maxmp, :atk  #getter and setter methods
  def initialize (name) # constroctor method
    self.hp = 50 #deafult values
    self.mp = 10
    self.speed = 5
    self.atk = 10
    self.ct = 0
    self.maxhp = 50
    self.maxhp = 10
    self.status = 'alive'
    ALL_UNITS << self
  end

  def attack(target) #Method a function that belongs to an object
    puts "#{self.name} attacked #{target.name}"
  end
end

class Squire < unit # inheritance

  def initialize (name)
  super(name) #function that calls the superclass's constroctor method
end
# we can specifize unique methods
#or we can overwrite methods from the parent by using the same name
def throw_stone(target)
  puts '#{self.name} threw a stone ...'
end
end

class Wizard < Unit
  def initialize(name)
    super(name)
    self.hp -= 10 # we can alter deafult values by specify only what is unique about wizard objects
    self.speed -= 2
    self.mp += 30
  end

  def cast()
    put "#{self.name} casted magic"
  end
end

class Knight < Unir
  def initialize(name)
    super(name)
    self.hp += 10
    self.atk += 5
    self.mp -= 5
end

def rend_armor()
  "#{self.name} rent armor! Everything is now rent!"
end
end
 def battle_is_over? #boolean function/method the "?" is purely for readibility these methods should only return t/f
   felled = []
   ALL_UNITS.each do |unit|
     if unit.status == "alive"
       felled << false
     else
       felled << true
   end
 end
 if felled.any?(false)
   return false #it's important to remember to return a t/f in a function
 end
 def take turn(u)
   puts "#{u.name}'s turn! what will you do?"
   puts  "1 - Attack\n2 - Special\n3 - wait"
   choice = gets.chomp.to_i
   case choice # cleaner syntax for an if statement 
   when 1
     puts "#{u.name} attacked"
   when 2
     puts "#{u.name} a speacial move!"
   when 3
     puts "waiting..."
   else
     puts "INVALID SELECTION"
end
end
  def start_battle
  battle_time = true
  white battle_time
  if battle_is_over?
 break # breaks out of loop
end
end
ALL_UNITS.each do |unit|
  sleep 0.1 # sleep will stall execution of the program for n seconds

  unit.ct += unit.speed
  if unit.ct >= 100
    unit.ct = 100
    take_turn(unit)
    unit.ct = 0
  end
end
end
end
 roy = knight.new('roy') # object.new is how we run class's constroctor method
 robin = wizard.new('robin')
 warth = squire.new('marth')
