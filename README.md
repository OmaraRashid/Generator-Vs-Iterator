# Generator-Vs-Iterator

in javascript we need to loop through the object to collect the data embedded in it to view of the user java script enable us to do that through iterations via iterator and in case you just need to call a function through multiple staging to ensure that the data are being processed through multiple stages here js offers the generator functions.

# What is iterators?

if you have an object and you want to collect the data within it all you shall do is to loop on that object and retrive the data from it java script object such as arrays or objects or sets what makes that avaible is that those java scripts objects implements Symbol.iterator those objects are called iterators. if the object doesn't have the Symbol.iterator property it won't be iteratable and called non-iteratables.

The logic behind iterability:

Data consumers: JavaScript has language constructs that consume data. For example, for-of loops over values and the spread operator (...) inserts values into Arrays or function calls.
Data sources: The data consumers could get their values from a variety of sources. For example, you may want to iterate over the elements of an Array, the key-value entries in a Map or the characters of a string.
# code
``` TypeScript
const Iterable = {
    [Symbol.iterator]() {
        let step = 0;
        const iterator = {
            next() {
                step++;
                if (step === 1)
                    return { value: 'Example', done: 'false' }
                else if (step === 2)
                    return { value: 'for', done: 'false' }
                else if (step === 3)
                    return { value: 'Iterator', done: 'false' }
                return { value: undefined, done: 'true' }
            }
        };
        return iterator;
    }
}
var iterator = Iterable[Symbol.iterator]();
iterator.next() // {value: 'Example', done: 'false'}
iterator.next() // {value: 'for', done: 'false'}
iterator.next() // {value: 'iterator', done: 'false'}
iterator.next() // {value: undefined, done: 'false'}
```
#Generators

The generator functions works as an async functions as they are function that excute untill the  keyword is found and when the function is recalled again the function will excute when from the yield keyowrd untill even it face other yield keyword or the function completes it's execution.

# code 
``` TypeScript
function* func() {
    // (A)
    console.log('First');
    yield;
    console.log('Second');
}
```
when the function is called it shall prints first whenever called again it shall prints Second. for the function to be generator we add the * sign before declaring it 
generator functions usage:
1. simpler asynchronous code
2. receiving asynchronous data using generators
3. Implementing Iterables

#Conclusion 
we have learned about Iterables,Iterators and generators.

Thanks for reading.
