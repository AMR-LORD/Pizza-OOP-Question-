# Pizza-OOP-Question-

## Requirements
Utilize OOP to create Pizza class which
1. Make dough
2. Adding Toppings
3. Bake
4. Calculate the price

price is calculated bu summing
1. `pizzaPrice` same for all
2.  `TypePrice` for the a specific pizza type
    - if small remain
    - if meduim multiply by 2
    - if extra multiply by 3
> Consider Using OOP Properties (`Encapsulation`, `Abstraction`, `Inheritance`, `Ploymorphism`)
```cpp
enum pizzaSize
{
    SMALL,
    MEDUIM,
    EXTRA
};

void MakeDough()
{
    cout << "Making Dough" << endl;
}

void Bake()
{
    cout << "Baking Pizza" << endl;
}

double CalcPizzaPrice(pizzaSize size, int TypePrice)
{
    double pizzaPrice = 50;
    switch (size)
    {
    case SMALL:
        TypePrice *= 1;
        break;
    case MEDUIM:
        TypePrice *= 2;
        break;
    case EXTRA:
        TypePrice *= 3;
        break;
    default:
        break;
    }
    return TypePrice + pizzaPrice;
}

void MakeChickenPizza(pizzaSize size)
{
    double TypePrice = 20;
    
    cout << "Making Chicken Pizza" << endl;
    MakeDough();
    cout << "Adding toppings for Chicken Pizza" << endl;
    Bake();
    cout << "Chicken Pizza finished" << endl;
    cout << "Price " << CalcPizzaPrice(size, TypePrice) << endl;
}

void MakeBeefPizza(pizzaSize size)
{
    double TypePrice = 30;

    cout << "Making Beef Pizza" << endl;
    MakeDough();
    cout << "Adding toppings for Beef Pizza" << endl;
    Bake();
    cout << "Beef Pizza finished" << endl;
    cout << "Price " << CalcPizzaPrice(size, TypePrice) << endl;
}
```
###### Output
```plaintext
Making Chicken Pizza
Making Dough
Adding toppings for Chicken Pizza
Baking Pizza
Chicken Pizza finished
Price 90
```
