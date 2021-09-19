# Enriching Your Python Classes With Dunder (Magic, Special) Methods

## What Are Dunder Methods?

In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:

    class NoLenSupport:
        pass

    >>> obj = NoLenSupport()
    >>> len(obj)
    TypeError: "object of type 'NoLenSupport' has no len()"

To fix this, you can add a __len__ dunder method to your class:

    class LenSupport:
        def __len__(self):
            return 42

    >>> obj = LenSupport()
    >>> len(obj)
    42

## Special Methods and the Python Data Model

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

For a beginner this might be slightly overwhelming at first though. No worries, in this article I will guide you through the use of dunder methods using a simple Account class as an example.

## Enriching a Simple Account Class

Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)

## Object Initialization: __init__

Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the __init__ dunder:

    class Account:
        """A simple account class"""

        def __init__(self, owner, amount=0):
            """
            This is the constructor that lets us create
            objects from this class
            """
            self.owner = owner
            self.amount = amount
            self._transactions = []

## Object Representation: __str__, __repr__

It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) There are two ways to do this using dunder methods:

1. __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

2. 

__str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

Let’s implement these two methods on the Account class:

    class Account:
        # ... (see above)

        def __repr__(self):
            return 'Account({!r}, {!r})'.format(self.owner, self.amount)

        def __str__(self):
            return 'Account of {} with starting amount: {}'.format(
                self.owner, self.amount)


## Iteration: __len__, __getitem__, __reversed__

In order to iterate over our account object I need to add some transactions. So first, I’ll define a simple method to add transactions. I’ll keep it simple because this is just setup code to explain dunder methods, and not a production-ready accounting system:

    def add_transaction(self, amount):
        if not isinstance(amount, int):
            raise ValueError('please use int for amount')
        self._transactions.append(amount)