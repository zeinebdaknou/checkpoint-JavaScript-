document.addEventListener('DOMContentLoaded', () => {
    const cart = document.getElementById('cart');
    const totalPriceElement = document.getElementById('total');
    
    // Update the total price
    function updateTotalPrice() {
        const itemPrices = document.querySelectorAll('.item-price');
        const quantities = document.querySelectorAll('.quantity');
        let total = 0;
        itemPrices.forEach((priceElement, index) => {
            const price = parseFloat(priceElement.textContent.replace('$', ''));
            const quantity = parseInt(quantities[index].textContent);
            total += price * quantity;
        });
        totalPriceElement.textContent = total.toFixed(2);
    }
    
    // Handle like button click
    cart.addEventListener('click', (event) => {
        if (event.target.classList.contains('like-button')) {
            event.target.classList.toggle('liked');
        }
    });
    
    // Handle delete button click
    cart.addEventListener('click', (event) => {
        if (event.target.classList.contains('delete-button')) {
            const item = event.target.closest('.item');
            item.remove();
            updateTotalPrice();
        }
    });
    
    // Handle quantity adjustments
    cart.addEventListener('click', (event) => {
        const item = event.target.closest('.item');
        const quantityElement = item.querySelector('.quantity');
        let quantity = parseInt(quantityElement.textContent);
        const priceElement = item.querySelector('.item-price');
        const price = parseFloat(priceElement.textContent.replace('$', ''));
        
        if (event.target.classList.contains('plus-button')) {
            quantity++;
        } else if (event.target.classList.contains('minus-button') && quantity > 1) {
            quantity--;
        }
        
        quantityElement.textContent = quantity;
        updateTotalPrice();
    });
});
