tacoCatInc.currentInventory = function() {
  let total = 0;

  // loop through every key in tacoCatInc
  for (let category in this) {

    // don't include cash in the inventory calculation
    if (category === 'cash') {
      continue;
    }

    // the value in each category is another object of items
    let items = this[category];

    // loop through each itemName in the category
    for (let itemName in items) {
      let itemObj = items[itemName];

      // add the product of each item's cost and quantity to the total
      total += itemObj.cost * itemObj.quantity;
    }

  }

  return total;
};

tacoCatInc.sale = function(order) {
  let finalPrice = 0;

  // loop through all of the categories in the order
  for (let category in order) {

    // the choices are the keys in the order object
    let choice = order[category];

    // add the cost of the choice to the final price
    finalPrice += this[category][choice].cost;

    // also add the cost of the choice to the cash property
    this.cash += this[category][choice].cost;

    // also subtract one from the quantity of the chosen item
    this[category][choice].quantity--;
  }

  return finalPrice;
}
