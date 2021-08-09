# 5 Design pattern of Java Script # 
 ## 1. module design pattern ## 
   This design pattern is most popular design pattern for maintaining particuler pieces of code independent of other code.Module are javascript classes It is        similar to the one of oops feature  which is called encapsulation which hide the data from outside the class by using public private access. for making this      we make closer in java script***
   Let’s look at a basic example:
  
      var counter = (function(){
        var priveteCounter = 0;
         function changeBy(val)
         {
            privateCounter += 1;
         }
         
         return {
           increment : function()
           {
              changeBy(1);//here we are creating closer because by using this we can access private data member and member function
           },

           decrement : function()
           {
              changeBy(-1);
           },
           
           value : function()
           {
              return  privateCounter ;
           }
         };
      
      })();
      
      consol.log(counter.value);
      
      counter.increment();
      
      consol.log(counter.value);
      
      counter.decrement();
      
      consol.log(counter.value);
   
  ## 2. Revealing Module Pattern ##
   
  It is an type of module design pattern with aditional feature here we make closer for both public and private properties.The purpose is to maintain                encapsulation and reveal certain variables and methods returned in an object literal. 
  Let’s look at a basic example:
    
    var Mountblue = (function(){
    var name = "suneja";
    var hello = function(){ console.log("Hello, " + name + "!");}
    var welcome = function() { console.log( hello() + " Welcome to Mountblue!");}
    return {
    name: name,
    sayHello: hello,
    sayWelcome: welcome
    }
    })();
    
    Mountblue.sayHello();
    Mountblue.sayWelcome();
    
  ## 3. constructor design pattern ##
  
  In object oriented programming language constructor are used to initialize the object. in javaScrip as everything in object for initializing we use               constructor . Constructor will call at the time of creation
  Let’s look at a basic example:
  
    function Student( name, age, city ) {

     this.name = name;
     this.age = age;
     this.city= city;

     this.toString = function () {
       return  " welcome " + this.name;
     };
    }
  
    var obj1 = new Student (suneja,20,mhow);
    console.log(obj1.toString());
  
  ## 4. prototype design pattern ##
  
  In prototype design pettern objects are created as clone or copy of created one specific object To clone an object, a constructor must exist to instantiate       the first object. Next, by using the keyword prototype variables and methods bind to the object’s structure. 
   Let’s look at a basic example:
  
  
      var car= function() {
        this.numWheels    = 4;
      }

      TeslaModelS.prototype = function() {

      var go = function() {
          console.log("car is running");
      };

      var stop = function() {
          console.log("car is stop");
      
      };

      return {
      pressBrakePedal: stop,
      pressGasPedal: go
      }

    }();
    
   ## 5. singleton design pattern ##
   
   A Singleton only allows for a single instantiation, but many instances of the same object. The Singleton creating multiple objects,after the first object          created, it will return instances of itself 
   
      class Singleton {
       static instance;
       constructor() {
       instance++;
       if(instance == 1)
       {
           Singleton.instance = new Singleton();
       }
     }
       static getInstance() {
       return Singleton.instance;
       }
    }
