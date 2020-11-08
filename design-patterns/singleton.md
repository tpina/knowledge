# Singleton

* Creational design pattern that restricts class to have only one instance
* Use when we need to ensure that only one instance of a given Object is available


```javascript
class Singleton {
	private static instance: Singleton

	private constructor() {}

	public static getInstance(): Singleton {
		if (!Singleton.instance) {
			Singleton.instance = new Singleton();
		}

		return Singleton.instance;
	}
}
```