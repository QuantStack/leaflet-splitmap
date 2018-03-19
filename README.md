# leaflet-splitmap

A Leaflet control to add a split screen to compare two map overlays.

**This project is a fork of the leaflet-side-by-side plugin**

![screencast example](screencast.gif)

### L.control.splitMap(_leftLayer[s]_, _rightLayer[s]_)

Creates a new Leaflet Control for comparing two layers or collections of layers. It does not add the layers to the map - you need to do that manually. Extends `L.Control` but `setPosition()` and `getPosition` are `noop` because the position is always the same - it does not make sense for this control to be in the corner like other Leaflet controls.

### Parameters

| parameter     | type           | description   |
| ----------    | -------------- | ------------- |
| `leftLayers`  | L.Layer\|array | A Leaflet Layer or array of layers to show on the left side of the map. Any layer added to the map that is in this array will be shown on the left |
| `rightLayers` | L.Layer\|array | A Leaflet Layer or array of layers to show on the right side of the map. Any layer added to the map that is in this array will be shown on the right. These *should not be* the same as any layers in `leftLayers` |
| `options`     | Object         | Options |
| `options.padding` | Number     | Padding between slider min/max and the edge of the screen in pixels. Defaults to `44` - the width of the slider thumb |

### Events

Subscribe to events using [these methods](http://leafletjs.com/reference.html#events)

| Event         | Data           | Description   |
| ----------    | -------------- | ------------- |
| `leftlayeradd`  | [LayerEvent](http://leafletjs.com/reference.html#layer-event) | Fired when a layer is added to the left-hand-side pane |
| `leftlayerremove` | [LayerEvent](http://leafletjs.com/reference.html#layer-event) | Fired when a layer is removed from the left-hand-side pane |
| `rightlayeradd` | [LayerEvent](http://leafletjs.com/reference.html#layer-event) | Fired when a layer is added to the right-hand-side pane |
| `rightlayerremove` | [LayerEvent](http://leafletjs.com/reference.html#layer-event) | You guessed it... fired when a layer is removed from the right-hand-side pane |
| `dividermove` | {x: Number} | Fired when the divider is moved. Returns an event object with the property `x` = the pixels of the divider from the left side of the map container. |

### Methods

| Method           | Returns        | Description   |
| ----------       | -------------- | ------------- |
| `setLeftLayers`  | `this`         | Set the layer(s) for the left side  |
| `setRightLayers` | `this`         | Set the layer(s) for the right side |

### Example

[Live Example](http://lab.digital-democracy.org/leaflet-side-by-side/) see [source](index.html)

### Limitations

- The divider is not movable with IE.
- Probably won't work in IE8, but what does?

### License

MIT
