# Dessert Order Form

A minimalist dessert order form with a subtle Japanese aesthetic design.

## Features

- **Single Selection**: Customers can select one dessert from five options
- **Japanese Aesthetic**: Clean design with earthy tones and minimal styling
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Simple Data Collection**: Collects name, dessert choice, and optional comments
- **Dietary Tags**: Clear labeling for gluten-free (gf) and dairy-free (df) options

## Dessert Menu

1. **Black Sesame Panna Cotta** (gf)
   - Creamy black sesame custard, kumquat compote, raspberry-yuzu gel, sesame tuile

2. **Hazelnut Espresso Cake** (gf)
   - Chocolate syphon cake, araguani crèmeux, hazelnut sponge cake, coffee glaze, hojicha-cacao ice cream

3. **Mikan** (gf)
   - Mandarin tart, satsuma mandarin curd, light sudachi mousse, orange chocolate mirror glaze, gold meringue

4. **Japanese Rice Pudding** (gf)
   - Arroz con leche, olive oil yogurt cake, cinnamon rice pudding mousse

5. **Sorbet of the Day** (gf, df)

## Usage

Simply open `dessert_order_form.html` in any web browser. The form is a single HTML file with embedded CSS and JavaScript - no dependencies required!

## Customization

### Connecting to a Backend

To connect this form to your backend, modify the `handleSubmit` function in the JavaScript section:

```javascript
function handleSubmit(event) {
    event.preventDefault();
    const formData = new FormData(event.target);
    const orderData = {
        name: formData.get('customerName'),
        dessert: formData.get('dessertChoice'),
        comments: formData.get('comments')
    };
    
    // Replace this with your API endpoint
    fetch('/api/orders', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(orderData)
    })
    .then(response => response.json())
    .then(data => {
        alert('Order submitted successfully!');
        event.target.reset();
    })
    .catch(error => console.error('Error:', error));
}
```

### Styling

The color palette can be easily customized by modifying the CSS variables:

- Background: `#f5f2ed` to `#e8e3db`
- Primary accent: `#c9a581`
- Text color: `#3d3d3d`
- Border color: `#d4cfc4`

## Design Philosophy

This form embraces the principles of Japanese design:
- **Ma (間)**: Negative space and breathing room
- **Shibui (渋い)**: Simple, subtle, and unobtrusive beauty
- **Wabi-sabi (侘寂)**: Finding beauty in imperfection and minimalism

## License

Free to use and modify for personal and commercial projects.

## Screenshots

*Coming soon*

---

Built with ❤️ for dessert lovers
