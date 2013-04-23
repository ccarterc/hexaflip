#![HexaFlip](http://oxism.com/images/hexaflip.png)
#[HexaFlip](http://oxism.com/hexaflip/)
### Transform arrays of any length into cubes with infinite sides.
### Featuring touch/mouse interaction, getter/setter methods, zero dependencies, and jQuery support.
[Dan Motzenbecker](http://oxism.com), MIT License

[@dcmotz](http://twitter.com/dcmotz)

Take a look at the [Codrops article](http://tympanus.net/codrops/2013/03/07/hexaflip-a-flexible-3d-cube-plugin)
for a guide through the process and some [demos](http://tympanus.net/Tutorials/HexaFlip).

## Basic Usage

Create an instance by passing a DOM element and a key-value set of arrays:

```javascript
var cubeSet = new HexaFlip(documentGetElementById('my-el'),
    {
        prince: ['For You', 'Prince', 'Dirty Mind', 'Controversy', '1999', 'Around the World in a Day'],
        curtis: ['Curtis', 'Roots', 'Super Fly', 'Back to the World', 'Got to Find a Way', 'Sweet Exorcist']
    }
);
```

If a value is a URL, HexaFlip will set that side to the image it points to, preloading it automatically.

You can also pass objects as values with `style` and `value` keys
for some meticulous customization of different sides.
Make the former an object literal of CSS properties to customize the styling of that cube face.


```javascript
var colorCube = new HexaFlip(documentGetElementById('color-cube'),
    {
        chromaSet: [
{
    value: 'orange',
    style: {
        backgroundColor: '#e67e22',
        fontWeight: 100
    }
},
{
    value: 'teal',
    style: {
        backgroundColor: '#1abc9c',
        fontFamily: 'Futura'
    }
},
{
    value: 'yellow',
    style: {
        backgroundColor: '#f1c40f',
        textDecoration: 'underline'
    }
}
        ]
    }
);
```

To enable horizontal rotation (like the photos above), pass it in the options:

```javascript
var horizontalCube = new HexaFlip(documentGetElementById('my-el2'),
    {
        letters: ['α', 'β', 'γ', 'δ', 'ε', 'ζ', 'η', 'θ', 'ι', 'κ', 'λ', 'μ',
      'ν', 'ξ', 'ο', 'π', 'ρ', 'σ', 'τ', 'υ', 'φ', 'χ', 'ψ', 'ω']
    },
    {
        horizontalFlip: true,
        size: 300
    }
);
```

To set and get the values of the cubes:

```javascript
cubeSet.setValue({ prince: '1999', curtis: 'Roots' });
cubeSet.getValue();
```

To rotate the cubes to the next or previous sides:

```javascript
cubeSet.flip();
cubeSet.flipBack();
```
