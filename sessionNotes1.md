/** Talk is cheap, show me the code! **/

E4 P1 - TOPICS
Building a Food Ordering App

> *First thing while building an app is "PLANNING"
> *If our planning is good, it is very easy to code

We should know what we are going to build > What is the process of building the app (how it would look)
UX design (Wireframe) -> UI Mock -> Then we code

PLANNING (Visually when things are available then its easy to code)
App Name - Yumito

Components (Major components):

> Header
> Body
> Footer

Header - logo, nav items/links(home, about, order, cart)
Body - Search bar, Search button, Resturant Container - {Resturant cards(Images, title, rating, cuisines, distance, price)}
Footer - Copyright, links, disclaimer, address, contact

Where all the components will reside - App Component
We need to create different components for each - Header, Body and Footer

Header component

- We need to add a logo and nav-items

const Header = () => {
return (

<div className="header">
<div className="logo-container">
<img
          className="logo-container"
          src="https://www.logodesign.net/logo/smoking-burger-with-lettuce-3624ld.png"
        />
</div>
<div className="nav-items">
<ul>
<li>Home</li>
<li>About</li>
<li>Contact Us</li>
<li>Cart</li>
</ul>
</div>
</div>
);
};

We are adding the "Header Component" inside our "AppLayout Component" - This is Composite composition

Just like Header component, we need a Body and Footer components which will be called in side the AppLayout

Body Component

> We need to add a search bar and a button
> We need to have resto-cards (we will need a lot)
> We will need to re-use the Resturant card, so we will create a seperate component for it
> Whenever we need a component to be re-used we use a component for it - IMP

There is one more way to write css - Inline CSS / Inline styles
style={Anything inside this}
Here the style takes a Javascript Object
Not a prefered way

const styleCard = {
backgroundColor: yellow;  
} // JS object

<div style={styleCard}></div>

It can be written like this too:

<div style={{ backgroundColor: "Red" }}></div>

Other way is using Material UI, Tailwind CSS, etc

Footer Component
Need to create a seperate component and call it inside AppLayout
