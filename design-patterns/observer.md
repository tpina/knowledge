# Observer

* Pattern in which objects get information about any events happening to the object they are observing
* Use when changes on one object may require updating other objects, and the actual set of objects is unknown or changes dynamically

```javascript
class Observable {
	private observers: Observer[] = [];

	public subscribe(observer: Observer): void {
		if (!this.observers.includes(observer)) {
			this.observers.push(observer);
		}
	}

	public unsubscribe(observer: Observer): void {
		const observerIndex = this.observers.indexOf(observer);

		if (observerIndex !== -1) {
			this.observers.splice(observer);
		}
	}

	public notify(): void {
		observers.forEach(observer => {
			observer.update(this);
		});
	}
}

class Observer {
	public update(observable: Observable): void {
		// do work...
	}
}
```
