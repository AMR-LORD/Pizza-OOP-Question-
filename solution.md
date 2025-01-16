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
