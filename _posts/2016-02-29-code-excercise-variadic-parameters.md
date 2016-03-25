---
layout: post 
title: "Variadic Parameters in Swift"
date: 2016-02-23
author: Doug Harper
tags: [Swift, Weekly Notes, Fundamentals]
published: true
---

While working on fundamentals of functions I ran across Variadic Parameters, which I've seen before but make more sense now.  
![Variadic Parameter Note]({{site.baseurl}}/images/Variadic_Parameters.png)

A variadic parameter accepts one or more values, which makes it very useful.  I can easily think of many situations when you'll need to enter data without knowing the number of data items -> like an estimator, recipes, sales figures, etc...

## Food Truck Excercise

The owner of a Food Truck wants keep track of daily total sales amounts.  The truck's crew should enter each sale as it occurs.

### First Attempt

    func totalSales(day: String = "Monday", saleAmount: Double...) {
        
        var sum = 0.0
    
        for sale in saleAmount {
            sum += sale
        }
    
      print("The total sales for \(day) is \(sum)")
    
    }

    let mondaysSales = totalSales(saleAmount: 34.56, 47.56)
    let tuesdaysSales = totalSales("Tuesday", saleAmount: 23.45, 67.21, 45.21)
    
I used a default parameter for day simple as an excercise since I'm practicing with parameters.  `saleAmount: Double...` is the variadic parameter and allows me to enter any number of sales into my function *i.e. 2 sales on Monday, 3 sales on Tuesday.*

## Refactor #1
    enum DayOfTheWeek{
      case Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday
    }
  
    func totalSales(day: DayOfTheWeek, saleAmount: Double...) {
    var sum = 0.0
    
    for sale in saleAmount {
        sum += sale
    }
    
    print("The total sales for \(day) is \(sum)")
    
    }
    
    totalSales(.Monday, saleAmount: 56.78, 34.56)
    totalSales(.Tuesday, saleAmount: 12.45, 45.78, 35.89)
    totalSales(.Wednesday, saleAmount: 12.45, 467.45, 25.78, 72.98, 109.87)
    
  Instead of creating 7 `let` or `vars` I set up an Enum for DaysOfTheWeek and threw it in place of my default parameter, which makes the code look much cleaner and easier to understand. 







