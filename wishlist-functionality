/**
 * Create the wishlist functionality of an e-shop that is selling vitamins.
 * (only the JS part)
 * 
 * Below is given the array of products and the array of wishlisted items
 * Both arrays contain objects.
 * 
 * The products array contains objects with product id, product name, product description, price and image source
 * 
 * The wishlist array contains objects with the product id and the user name.
 * 
 * The user should be able to press a heart on the product card 
 * and the specific product should be added to a list of his favorite products.
 * 
 * If the product is already in the wishlist then it should be removed
 * 
 * 
 * Scenario: each product card contains a heart. Once the heart is pressed it should change color.
 * When the colored heart is pressed, then the product should be removed from the wishlist
 * 
 * a) implement a function that adds the product id along with the user name to the wishlist array
 * if the product id for the specific user is in the wishlist then remove it
 * 
 * Scenario:
 * When the user visits his favorites page, 
 * then he should able to see a list of his whishlisted products. 
 * (The list should contain all product details such as description, 
 * price, images etc)
 * b) implement a function that removes the specific product from the wishlist array
 * 
 * Scenario: User wants to see his wishlisted products
 * c) implement a function that lists all the products that their ids are contained in the wishlist for the specific user
 * Output should be like:
 * 
 * For user george here is the wishlist:
 * - D3 5000 iu
 *   Takes care of your immune system
 *   Price: 10€
 *   <img src="http://example.com/1/">
 * 
 */

// Sample Data
let products = [
    { // 1
        id: 1,
        name: "D3 5000 iu",
        description: 'Takes care of your immune system',
        price: 10,
        image: 'http://example.com/1'
    },
    { // 2
        id: 2,
        name: "C 1000mg",
        description: '180 tabs of vitamin C with Bioflanoids',
        price: 3,
        image: 'http://example.com/23'
    },
    { // 3
        id: 3,
        name: "B - Complex 50 mg",
        description: 'Balanced mix of all basic B vitamins',
        price: 12,
        image: 'http://example.com/44'
    },
    { // 4
        id: 4,
        name: "Cal-Mag",
        description: 'Calcium and Magnesium in the proper analogy',
        price: 15,
        image: 'http://example.com/123'
    },
    { // 5
        id: 5,
        name: "E 400iu",
        description: 'Best for skin issues',
        price: 10,
        image: 'http://example.com/456'
    }
];

let wishlist = [
    {
        user: 'alkis',
        productId: 1
    },
    {
        user: 'alkis',
        productId: 2
    },
    {
        user: 'george',
        productId: 1
    }
];

console.log('\n"`-._,-\'"`-._,-\'"`-._,-\'"`(^,^)-._,-\'"`-._,-\'"`-._,-\'"`-._,-\'"`-._,-\'"`-._,-\'"\n');
/** a) implement a function that adds the product id along with the user name to the wishlist array
 * if the product id for the specific user is in the wishlist then remove it
 * b) implement a function that removes the specific product from the wishlist array 
 **/
// a & b:
function addToWishlist({ user, productId }) {
    let item = { user, productId };
    if (!wishlist.some(value => { if (JSON.stringify(value) == JSON.stringify(item)) return wishlist.splice(wishlist.indexOf(value), 1) }))
        wishlist.push(item);
    return wishlist;
}

let wishlistObject4 = { productId: 5, user: 'george' };
console.log('0:', wishlist);
console.log('a:', addToWishlist(wishlistObject4));
console.log('b:', addToWishlist(wishlistObject4));
// console.log('3:', addToWishlist(wishlistObject4));
// console.log('3:', addToWishlist(wishlistObject4));

/** c) implement a function that lists all the products that their ids are contained in the wishlist for the specific user
* Output should be like:
* 
* For user george here is the wishlist:
* - D3 5000 iu
*   Takes care of your immune system
*   Price: 10€
*   <img src="http://example.com/1/">
*
*/
// c:
function printWishlist(aUser) {
    let userProducts = [];
    let output = '';
    for (li of wishlist)
        if (li.user == aUser) {
            userProducts.push(li.productId);
            output = `\nFor user ${aUser} here is the wishlist:\n`;
        }
    if (output == '')
        output = `\nFor user ${aUser} the wishlist is empty.\n`;
    else
        for (id of userProducts)
            for (product of products)
                if (id == product.id)
                    for (key in product) {
                        if (key != "id") {
                            if (key == "name")
                                output += '- ';
                            else
                                output += '  '
                            if (key == "price")
                                output += 'Price: ';
                            else if (key === "image")
                                output += '<img src="';
                            output += product[key] + `${key === "image" ? '/">' : ''}${key === "price" ? '€' : ''} \n`;
                        }
                    }
    console.log(output);
    return output;
}

console.log('c:')
printWishlist('george');

console.log('\n~ "\'-,_.-`" c - . o _ , d - \' e " ` d - . _ , -\' "  b ` - y . _  R - a \' m - i  _ ,-\'"` (^-^) - ._. - A - l " ` - S - _ - a - \' - a - _ - d _ , - i  - _ , - \' " ` - . _ ,   - \' " ` - . _ , - \' " \n');
