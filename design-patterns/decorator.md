# Decorator

* Pattern that lets you add new characteristics to objects by adding a wrapper that contains the behaviors
* Use when it's necessary to add these extra behaviors on run time, or when inheritance is not possible

```javascript
interface Coffee {
	getCost(): int;
}

class SimpleCoffee implements Coffee {
	public getCost(): int {
		return 2;
	}
}

class CoffeeDecorator implements Coffee {
	protected decoratedCoffee: SimpleCoffee;

	constructor(decoratedCoffee: SimpleCoffee) {
		this.decoratedCoffee = decoratedCoffee;
	}

	public getCost(): int {
		return this.decoratedCoffee.getCost();
	}
}

class CoffeeWithMilk extends CoffeeDecorator {
	public getCost(): int {
		return super.getCost() + 0.5;
	}
}
```