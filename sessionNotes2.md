E4 P2 - TOPICS
Building a Food Ordering App

How do we make our cards dynamic?

Props

> In react we have something called as Props (Also called as Properties)
> It is something that we can pass to a component
> Suppose we want to dynamically pass data to a component -> We make use of props - Very Important
> Props -> Are just normal arguments to a function
> Passing a argument to a function = Passing a prop to a component
> passing props to a component
> Wraps it inside a component and passes it as props
> Props is just a javascript object
> React will wrap them as a object and it will pass the value inside the component

To access this props which is a JS object we pass it inside curly brackets {}
{props.resName}
{props.cuisines}

> Destructuring on the fly

Here we are passing the props
<ResturantCard
          resName="Priyadarshini Veg"
          cuisine="South India, North Indian"
        />
<ResturantCard
          resName="Shiv Sagar"
          cuisine="South India, North Indian, Asian"
        />
The value is used inside the ResturantCard

const ResturantCard = (props) => {
console.log(props);
return (

<div className="res-card">
<h4>{props.resName}</h4>
<h5>{props.cuisine}</h5>
<h5>4.5 stars</h5>
<h5>38 mins</h5>
</div>
);
};

Now let us destructure on the fly in the component
const ResturantCard = ({ resName, cuisine }) => {
//...

<div className="res-card">
<h4>{resName}</h4>
<h5>{cuisine}</h5>
}

We can directly use the prop value instead of converting it like props.resName (Both are the same thing)

Another way to do this is:
const ResturantCard = (props) => {
const {resName, cuisine} = props
}

<ResturantCard
          resName="Priyadarshini Veg"
          cuisine="South India, North Indian"
        />
<ResturantCard
          resName="Shiv Sagar"
          cuisine="South India, North Indian, Asian"
        />

React is wrappring these props (resName="Shiv Sagar" , cuisine="South India, North Indian, Asian") into a object
and passes it into the component and then destructures it.

This is more readable

> How does data come from backend to us?

It comes in the form of a JSON

> Config Driven UI (useful in front end system design interviews)

- Suppose we have offers in Bangalore, We might have some other offers in Delhi ( these cards will be different in every city)

* There might be no offers in some city.

- Our website is driven by DATA / configs - This is known as config driven UI
- Controlling your UI (how the UI looks like) using data/config which comes from backend
- UI is powered by data
- UI layer + Data layer = FrontEnd

Important Concept
const resObj = {
.... Some data
}

What ever we pass over here (i.e this key resData -> will be passed while destructuring it)
<ResturantCard resData={resObj} />

const ResturantCard = (props) => {
const {resData} = props
}

The value of resData={Javascript object i.e resObj}

resData(prop)={resObj}(argument/object)

Best practices of writing our code:

1. Destructuring our code initially - We use optional chaining (?.)
   Ex. resData?.info

2. Looping our dynamic data
   We use map function for this
   Best way is to use map,filter and reduce - Imp

{resList.map((resturant) => (
<ResturantCard resData={resturant} />
))}

Here we are using the resList.map for each resturant, we are rendering a resturant card

Warning!
index.js:1 Warning: Each child in a list should have a unique "key" prop.
Each of the list item should be uniquely represented (unique key)

key is reserved word
key={resturant.data.id}

When we make use of .map() we should always give a unique key
