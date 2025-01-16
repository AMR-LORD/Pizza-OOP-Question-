## Pizza Class
```cpp
class Pizza
{
public:
    enum pizzaSize
    {
        SMALL,
        MEDUIM,
        EXTRA
    };

protected:
    virtual string getName() = 0;
    virtual double getTypePrice() = 0;

private:
    const double pizzaPrice = 50;
    pizzaSize size;

    void MakeDough()
    {
        cout << "Making Dough" << endl;
    }

    void Bake()
    {
        cout << "Baking Pizza" << endl;
    }

    void AddToppings()
    {
        cout << "Adding toppings for " << getName() << " pizza" << endl;
    }

    void printMaking()
    {
        cout << "Making " << getName() << " pizza" << endl;
    }

    void printEnd()
    {
        cout << getName() << " pizza finished" << endl;
    }

    double calcPrice(pizzaSize size)
    {
        double temoTypePrice = getTypePrice();
        switch (size)
        {
        case SMALL:
            temoTypePrice *= 1;
            break;
        case MEDUIM:
            temoTypePrice *= 2;
            break;
        case EXTRA:
            temoTypePrice *= 3;
            break;
        default:
            break;
        }
        return temoTypePrice + pizzaPrice;
    }

public:
    void MakePizza(pizzaSize size)
    {
        printMaking();
        MakeDough();
        AddToppings();
        Bake();
        cout << calcPrice(size) << endl;
    }
};
```
## Inherited Classes
### Chicken Pizza
```cpp
class ChickenPizza : public Pizza
{
    string getName() override
    {
        return "Chicken";
    }
    double getTypePrice() override
    {
        return 30;
    }
};
```
### Chicken Pizza
```cpp
class MushroomPizza : public Pizza
{
    string getName() override
    {
        return "Mushroom";
    }
    double getTypePrice() override
    {
        return 20;
    }
};
```
### Beef Pizza
```cpp
class BeefPizza : public Pizza
{
    string getName() override
    {
        return "Beef";
    }
    double getTypePrice() override
    {
        return 50;
    }
};
```
## Main Function
```cpp
Pizza* pizza;

Pizza::pizzaSize size;


int choice, sizeNum;

cout << "Enter your choice ( 1 for beef, 2 for chicken ) : ";

cin >> choice;

cout << "\nEnter the size ( 1 for small, 2 for medium, 3 for large ) : ";

cin >> sizeNum;
cout << endl;

switch(sizeNum)
{
case 1:
    size = Pizza::pizzaSize::SMALL;
    break;
case 2:
    size = Pizza::pizzaSize::MEDUIM;
    break;
case 3:
    size = Pizza::pizzaSize::EXTRA;
    break;
default:
    break;
}

switch (choice)
{
case 1:
    pizza = new BeefPizza();
    break;
case 2:
    pizza = new ChickenPizza();
    break;
default:
    pizza = new ChickenPizza();
    break;
}
pizza->MakePizza(size);
```
## Output
```plaintext
Enter your choice ( 1 for beef, 2 for chicken ) : 1

Enter the size ( 1 for small, 2 for medium, 3 for large ) : 2

Making Beef pizza
Making Dough
Adding toppings for Beef pizza
Baking Pizza
150
```
