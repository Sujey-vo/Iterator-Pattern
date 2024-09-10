# Iterator-Pattern

// Implementación simple del patrón Iterator

class ConcreteIterator {
    constructor(collection) {
        this.collection = collection;
        this.position = 0;
    }

    hasNext() {
        return this.position < this.collection.length;
    }

    next() {
        if (this.hasNext()) {
            return this.collection[this.position++];
        }
        return null;
    }
}

class ConcreteCollection {
    constructor(items) {
        this.items = items;
    }

    createIterator() {
        return new ConcreteIterator(this.items);
    }
}

// Ejemplo de uso
const items = ["A", "B", "C", "D"];
const collection = new ConcreteCollection(items);
const iterator = collection.createIterator();

while (iterator.hasNext()) {
    console.log(iterator.next());
}
