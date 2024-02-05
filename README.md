import React, { useState } from 'react';
import './App.css'; // Import your CSS file for styling

const App = () => {
  const [cart, setCart] = useState([]);
  const candies = [
    { name: 'Choco1', description: 'Delicious chocolate', price: 2.5 },
    { name: 'Choco2', description: 'Yummy chocolate bar', price: 1.8 },
    { name: 'Choco3', description: 'Smooth milk chocolate', price: 3.0 },
    { name: 'Choco4', description: 'Dark chocolate delight', price: 2.2 },
  ];

  const addToCart = (candy, option) => {
    const updatedCart = [...cart, { ...candy, option }];
    setCart(updatedCart);
  };

  return (
    <div className="app">
      <header>
        <div className="column">Candy Name</div>
        <div className="column">Description</div>
        <div className="column">Price</div>
        <div className="column">Add</div>
      </header>

      <div className="candy-list">
        {candies.map((candy, index) => (
          <div className="candy-row" key={index}>
            <div className="column">{candy.name}</div>
            <div className="column">{candy.description}</div>
            <div className="column">{candy.price}</div>
            <div className="column">
              <button onClick={() => addToCart(candy, 'Add1')}>Add1</button>
              <button onClick={() => addToCart(candy, 'Add2')}>Add2</button>
              <button onClick={() => addToCart(candy, 'Add3')}>Add3</button>
            </div>
          </div>
        ))}
      </div>

      <div className="cart">
        <h2>Cart</h2>
        <div className="cart-details">
          {cart.map((item, index) => (
            <div key={index} className="cart-item">
              <div>{item.name}</div>
              <div>{item.option}</div>
              <div>{item.price}</div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
};

export default App;
