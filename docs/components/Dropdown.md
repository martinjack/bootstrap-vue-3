# Dropdown

> Dropdowns are toggleable, contextual overlays for displaying lists of links and actions in a
> dropdown menu format.

`<b-dropdown>` components are toggleable, contextual overlays for displaying lists of links and more. They're toggled by clicking (or pressing space or enter when focused), not by hovering; this is an [intentional design decision](https://markdotto.com/2012/02/27/bootstrap-explained-dropdowns/).

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
        <b-dropdown-item>First Action</b-dropdown-item>
        <b-dropdown-item>Second Action</b-dropdown-item>
        <b-dropdown-item>Third Action</b-dropdown-item>
        <b-dropdown-divider></b-dropdown-divider>
        <b-dropdown-item active>Active action</b-dropdown-item>
        <b-dropdown-item disabled>Disabled action</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
    <b-dropdown-item>First Action</b-dropdown-item>
    <b-dropdown-item>Second Action</b-dropdown-item>
    <b-dropdown-item>Third Action</b-dropdown-item>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item active>Active action</b-dropdown-item>
    <b-dropdown-item disabled>Disabled action</b-dropdown-item>
  </b-dropdown>
</div>
```

## Button content

You can customize the text of the dropdown button by using either the `text` prop (shown in previous
examples), or use the `button-content` slot instead of the `text` prop. The `button-content` slot
allows you to use basic HTML and icons in the button content.

If both the prop `text` and slot `button-content` are present, the slot `button-content` will take
precedence.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown text="Button text via Prop" class="m-1">
        <b-dropdown-item href="#">An item</b-dropdown-item>
        <b-dropdown-item href="#">Another item</b-dropdown-item>
      </b-dropdown>
      <b-dropdown  class="m-1">
        <template #button-content>
        Custom <strong>Content</strong> with <em>HTML</em> via Slot
        </template>
        <b-dropdown-item href="#">An item</b-dropdown-item>
        <b-dropdown-item href="#">Another item</b-dropdown-item>
      </b-dropdown>
    </div>

  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown text="Button text via Prop" class="m-1">
    <b-dropdown-item href="#">An item</b-dropdown-item>
    <b-dropdown-item href="#">Another item</b-dropdown-item>
  </b-dropdown>

  <b-dropdown class="m-1">
    <template #button-content>
      Custom <strong>Content</strong> with <em>HTML</em> via Slot
    </template>
    <b-dropdown-item href="#">An item</b-dropdown-item>
    <b-dropdown-item href="#">Another item</b-dropdown-item>
  </b-dropdown>
</div>
```

## Positioning

Dropdown supports various positioning such as left and right aligned, dropdown and dropup, and
supports auto-flipping (dropdown to dropup, and vice-versa) when the menu would overflow off of the
visible screen area.

### Menu alignment

The dropdown menu can either be left aligned (default) or right aligned with respect to the button
above it. To have the dropdown aligned on the right, set the `right` prop.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-left" text="Left align" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
      <b-dropdown id="dropdown-right" right text="Right align" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-left" text="Left align" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>

  <b-dropdown id="dropdown-right" right text="Right align" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

### Dropup

Turn your dropdown menu into a drop-up menu by setting the `dropup` prop.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-dropup" dropup text="Drop-Up" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-dropup" dropup text="Drop-Up" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

### Drop right or left

Turn your dropdown menu into a drop-right menu by setting the `dropright` prop. Or, turn it into a
drop-left menu by setting the `dropleft` right prop to true.

`dropright` takes precedence over `dropleft`. Neither `dropright` or `dropleft` have any effect if
`dropup` is set.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-dropright" dropright text="Drop-Right" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
      <b-dropdown id="dropdown-dropleft" dropleft text="Drop-Left" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
          <b-dropdown-item href="#">Another action</b-dropdown-item>
          <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
    </div>

  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-dropright" dropright text="Drop-Right" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>

  <b-dropdown id="dropdown-dropleft" dropleft text="Drop-Left" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

### Auto "flipping"

By default, dropdowns may flip to the top, or to the bottom, based on their current position in the
viewport. To disable this auto-flip feature, set the `no-flip` prop.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown text="No flipping" no-flip>
        <b-dropdown-item href="#">An item</b-dropdown-item>
        <b-dropdown-item href="#">Another item</b-dropdown-item>
        <b-dropdown-item href="#">Yet Another item</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown text="No flipping" no-flip>
    <b-dropdown-item href="#">An item</b-dropdown-item>
    <b-dropdown-item href="#">Another item</b-dropdown-item>
    <b-dropdown-item href="#">Yet Another item</b-dropdown-item>
  </b-dropdown>
</div>
```

### Menu offset

Like to move your menu away from the toggle buttons a bit? Then use the `offset` prop to specify the
number of pixels to push right (or left when negative) from the toggle button:

- Specified as a number of pixels: positive for right shift, negative for left shift.
- You can specify two values to set the offset for horizontal and vertical offset. For example 10, 25 pushes the menu 10 pixels right and 25 pixels down.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-offset" offset="25" text="Offset Dropdown" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
      <b-dropdown id="dropdown-offset" offset="20, 30" text="Offset Dropdown 2 dimensions" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-offset" offset="25" text="Offset Dropdown" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
  <b-dropdown id="dropdown-offset" offset="20, 30" text="Offset Dropdown 2 dimensions" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

### Boundary constraint

By default, dropdowns are visually constrained to its scroll parent, which will suffice in most
situations. However, if you place a dropdown inside an element that has `overflow: scroll` (or
similar) set, the dropdown menu may - in some situations - get cut off. To get around this, you can
specify a boundary element via the `boundary` prop. Supported values are `'scrollParent'` (the
default), `'viewport'`, `'window'` or a reference to an HTML element. The boundary value is passed
directly to Popper.js's `boundariesElement` configuration option.

**Note:** When `boundary` is any value other than the default of `'scrollParent'`, the style
`position: static` is applied to the dropdown component's root element in order to allow the menu
to "break-out" of its scroll container. In some situations this may affect your layout or
positioning of the dropdown trigger button. In these cases you may need to wrap your dropdown inside
another element.

### Dropdown auto close behavior

By default, the dropdown menu is closed when clicking inside or outside the dropdown menu. You can use the `auto-close` property to change this behavior of the dropdown.
The `auto-close`property has 4 options

- `true` : the dropdown will be closed by clicking outside or inside the dropdown menu.
- `false` : the dropdown will be closed by clicking the toggle button and manually calling hide method. (Also will not be closed by pressing <kbd>esc</kbd> key)
- `inside` : the dropdown will be closed (only) by clicking inside the dropdown menu.
- `outside` : the dropdown will be closed (only) by clicking outside the dropdown menu.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-default" text="Default Dropdown" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here</b-dropdown-item-button>
      </b-dropdown>
      <b-dropdown id="dropdown-inside" text="Clickable outside (auto-close=inside)" auto-close="inside" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here</b-dropdown-item-button>
      </b-dropdown>
      <b-dropdown id="dropdown-outside" text="Clickable inside (auto-close=outside)" auto-close="outside" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here</b-dropdown-item-button>
      </b-dropdown>
      <b-dropdown id="dropdown-false" text="Manual close (auto-close=false)" :auto-close="false" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here</b-dropdown-item-button>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-default" text="Default Dropdown" class="m-2">
    <b-dropdown-item-button>Action</b-dropdown-item-button>
    <b-dropdown-item-button>Another action</b-dropdown-item-button>
    <b-dropdown-item-button>Something else here</b-dropdown-item-button>
  </b-dropdown>
  <b-dropdown
    id="dropdown-inside"
    text="Clickable outside (auto-close=inside)"
    auto-close="inside"
    class="m-2"
  >
    <b-dropdown-item-button>Action</b-dropdown-item-button>
    <b-dropdown-item-button>Another action</b-dropdown-item-button>
    <b-dropdown-item-button>Something else here</b-dropdown-item-button>
  </b-dropdown>
  <b-dropdown
    id="dropdown-outside"
    text="Clickable inside (auto-close=outside)"
    auto-close="outside"
    class="m-2"
  >
    <b-dropdown-item-button>Action</b-dropdown-item-button>
    <b-dropdown-item-button>Another action</b-dropdown-item-button>
    <b-dropdown-item-button>Something else here</b-dropdown-item-button>
  </b-dropdown>
  <b-dropdown
    id="dropdown-false"
    text="Manual close (auto-close=false)"
    :auto-close="false"
    class="m-2"
  >
    <b-dropdown-item-button>Action</b-dropdown-item-button>
    <b-dropdown-item-button>Another action</b-dropdown-item-button>
    <b-dropdown-item-button>Something else here</b-dropdown-item-button>
  </b-dropdown>
</div>
```

### Advanced Popper.js configuration

If you need some advanced Popper.js configuration to make dropdowns behave to your needs, you can
use the `popper-opts` prop to pass down a custom configuration object which will be deeply merged
with the BootstrapVue defaults.

Head to the [Popper.js docs](https://popper.js.org/docs/v1/) to see all the configuration options.

**Note**: The props `offset`, `boundary` and `no-flip` may lose their effect when you overwrite the
Popper.js configuration.

## Split button support

Create a split dropdown button, where the left button provides standard `click` event and link
support, while the right-hand side is the dropdown menu toggle button.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown split text="Split Dropdown" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here...</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown split text="Split Dropdown" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here...</b-dropdown-item>
  </b-dropdown>
</div>
```

### Split button link support

The left split button defaults to an element of type `<button>` (a `<b-button>` to be exact). To
convert this button into a link or `<router-link>`, specify the href via the `split-href` prop or a
router link `to` value via the `split-to` prop, while maintaining the look of a button.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown split split-href="#foo/bar" text="Split Link" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here...</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown split split-href="#foo/bar" text="Split Link" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here...</b-dropdown-item>
  </b-dropdown>
</div>
```

### Split button type

The split button defaults to a button `type` of `'button'`. You can specify an alternate type via
the `split-button-type` prop. Supported values are: `'button'`, `'submit'` and `'reset'`.

If props `split-to` or `split-href` are set, the `split-button-type` prop will be ignored.

## Styling options

Dropdowns support various props for styling the dropdown trigger button.

### Sizing

Dropdowns work with trigger buttons of all sizes, including default and split dropdown buttons.

Set the `size` prop to either `sm` for small button(s), or `lg` for large button(s).

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown size="lg" text="Large" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here</b-dropdown-item-button>
        </b-dropdown>
        <b-dropdown size="lg" split text="Large Split" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
      </b-dropdown>
    </div>
    <div>
      <b-dropdown size="sm" text="Small" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
        </b-dropdown>
        <b-dropdown size="sm" split text="Small Split" class="m-2">
        <b-dropdown-item-button>Action</b-dropdown-item-button>
        <b-dropdown-item-button>Another action</b-dropdown-item-button>
        <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
      </b-dropdown>
    </div>  
  </b-card>
</ClientOnly>

```html
<div>
  <div>
    <b-dropdown size="lg" text="Large" class="m-2">
      <b-dropdown-item-button>Action</b-dropdown-item-button>
      <b-dropdown-item-button>Another action</b-dropdown-item-button>
      <b-dropdown-item-button>Something else here</b-dropdown-item-button>
    </b-dropdown>

    <b-dropdown size="lg" split text="Large Split" class="m-2">
      <b-dropdown-item-button>Action</b-dropdown-item-button>
      <b-dropdown-item-button>Another action</b-dropdown-item-button>
      <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
    </b-dropdown>
  </div>
  <div>
    <b-dropdown size="sm" text="Small" class="m-2">
      <b-dropdown-item-button>Action</b-dropdown-item-button>
      <b-dropdown-item-button>Another action</b-dropdown-item-button>
      <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
    </b-dropdown>

    <b-dropdown size="sm" split text="Small Split" class="m-2">
      <b-dropdown-item-button>Action</b-dropdown-item-button>
      <b-dropdown-item-button>Another action</b-dropdown-item-button>
      <b-dropdown-item-button>Something else here...</b-dropdown-item-button>
    </b-dropdown>
  </div>
</div>
```

**Note:** _changing the size of the button(s) does not affect the size of the menu items!_

### Dropdown color variants

The dropdown toggle button can have one of the standard Bootstrap contextual variants applied by
setting the prop `variant` to `success`, `primary`, `info`, `danger`, `link`, `outline-dark`, etc.
(or custom variants, if defined). The default variant is `secondary`.

See the [Variant Reference](/docs/reference/color-variants) for a full list of built-in contextual
variants.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown text="Primary" variant="primary" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
      <b-dropdown text="Success" variant="success" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
      <b-dropdown text="Outline Danger" variant="outline-danger" class="m-2">
        <b-dropdown-item href="#">Action</b-dropdown-item>
        <b-dropdown-item href="#">Another action</b-dropdown-item>
        <b-dropdown-item href="#">Something else here</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown text="Primary" variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>

  <b-dropdown text="Success" variant="success" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>

  <b-dropdown text="Outline Danger" variant="outline-danger" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

You can also apply arbitrary classes to the toggle button via the `toggle-class` prop. This prop
accepts either a string or array of strings.

### Split button color variant

By default, the left split button uses the same `variant` as the `toggle` button. You can give the
split button its own variant via the `split-variant` prop.

<ClientOnly>
  <b-card>
    <b-dropdown
        split
        split-variant="outline-primary"
        variant="primary"
        text="Split Variant Dropdown"
        class="m-2"
    >
      <b-dropdown-item href="#">Action</b-dropdown-item>
      <b-dropdown-item href="#">Another action</b-dropdown-item>
      <b-dropdown-item href="#">Something else here...</b-dropdown-item>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown
    split
    split-variant="outline-primary"
    variant="primary"
    text="Split Variant Dropdown"
    class="m-2"
  >
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here...</b-dropdown-item>
  </b-dropdown>
</div>
```

### Dark mode

You can render the dropdown menu in dark mode by setting the `dark` property.
<ClientOnly>
<b-card>

<div>
<b-dropdown id="dropdown-1" text="Dropdown Button" dark class="m-md-2">
<b-dropdown-item>First Action</b-dropdown-item>
<b-dropdown-item>Second Action</b-dropdown-item>
<b-dropdown-item>Third Action</b-dropdown-item>
<b-dropdown-divider></b-dropdown-divider>
<b-dropdown-item active>Active action</b-dropdown-item>
<b-dropdown-item disabled>Disabled action</b-dropdown-item>
</b-dropdown>
</div>
</b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-1" text="Dropdown Button" dark class="m-md-2">
    <b-dropdown-item>First Action</b-dropdown-item>
    <b-dropdown-item>Second Action</b-dropdown-item>
    <b-dropdown-item>Third Action</b-dropdown-item>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item active>Active action</b-dropdown-item>
    <b-dropdown-item disabled>Disabled action</b-dropdown-item>
  </b-dropdown>
</div>
```

### Block level dropdowns

By default, dropdowns act like buttons and are displayed inline. To create block level dropdowns
(that span to the full width of a parent) set the `block` prop. Both, regular and split button
dropdowns are supported.

<ClientOnly>
  <b-card>
    <b-dropdown text="Block Level Dropdown" block variant="primary" class="m-2">
      <b-dropdown-item href="#">Action</b-dropdown-item>
      <b-dropdown-item href="#">Another action</b-dropdown-item>
      <b-dropdown-item href="#">Something else here</b-dropdown-item>
    </b-dropdown>
    <b-dropdown
      text="Block Level Split Dropdown"
      block
      split
      split-variant="outline-primary"
      variant="primary"
      class="m-2"
    >
      <b-dropdown-item href="#">Action</b-dropdown-item>
      <b-dropdown-item href="#">Another action</b-dropdown-item>
      <b-dropdown-item href="#">Something else here...</b-dropdown-item>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown text="Block Level Dropdown" block variant="primary" class="m-2">
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>

  <b-dropdown
    text="Block Level Split Dropdown"
    block
    split
    split-variant="outline-primary"
    variant="primary"
    class="m-2"
  >
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here...</b-dropdown-item>
  </b-dropdown>
</div>
```

If you want the dropdown menu to span to the full width of the parent container too, add the `w-100`
utility class to the `menu-class` prop.

<ClientOnly>
  <b-card>
    <b-dropdown
      text="Block Level Dropdown Menu"
      block
      variant="primary"
      class="m-2"
      menu-class="w-100"
    >
      <b-dropdown-item href="#">Action</b-dropdown-item>
      <b-dropdown-item href="#">Another action</b-dropdown-item>
      <b-dropdown-item href="#">Something else here</b-dropdown-item>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown
    text="Block Level Dropdown Menu"
    block
    variant="primary"
    class="m-2"
    menu-class="w-100"
  >
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here</b-dropdown-item>
  </b-dropdown>
</div>
```

### Dropdown sub-component color variants

Many of the supported dropdown [sub-components](#dropdown-supported-sub-components) provide a
`variant` prop for controlling their text color.

### Hidden caret

The dropdown can be created with the toggle's caret visually hidden by setting the `no-caret` prop
to `true`. This is useful when the dropdown is to be displayed as an icon.

<ClientOnly>
  <b-card>
    <b-dropdown size="lg" variant="link" toggle-class="text-decoration-none" no-caret>
      <template #button-content> &#x1f50d;<span class="visually-hidden">Search</span> </template>
      <b-dropdown-item href="#">Action</b-dropdown-item>
      <b-dropdown-item href="#">Another action</b-dropdown-item>
      <b-dropdown-item href="#">Something else here...</b-dropdown-item>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown size="lg" variant="link" toggle-class="text-decoration-none" no-caret>
    <template #button-content> &#x1f50d;<span class="visually-hidden">Search</span> </template>
    <b-dropdown-item href="#">Action</b-dropdown-item>
    <b-dropdown-item href="#">Another action</b-dropdown-item>
    <b-dropdown-item href="#">Something else here...</b-dropdown-item>
  </b-dropdown>
</div>
```

**Note:** The caret will always be shown when using `split` mode.

## Dropdown supported sub-components

The following components can be placed inside your dropdowns. Using any other component or markup
may break layout and/or keyboard navigation.
| Sub-component | Description |
| ----------------- | ---------------------------- |
| `<b-dropdown-item>` | Action items that provide click, link, and `<router-link>`/`<nuxt-link>` functionality. Renders as an `<a>` element by default. |
| <span style="white-space:nowrap;">`<b-dropdown-item-button>`</span> | An alternative to `<b-dropdown-item>` that renders a menu item using a `<button>` element. |
| `<b-dropdown-divider>` | A divider / spacer which can be used to separate dropdown items. |
| `<b-dropdown-text>` | Free flowing text content in a menu. |
| `<b-dropdown-group>` | For grouping dropdown sub-components with an optional header. |
| `<b-dropdown-header>` | A header item, used to help identify a group of dropdown items. |

**Note:** _Nested sub-menus are **not** supported._

### `<b-dropdown-item>`

The `<b-dropdown-item>` is typically used to create a navigation link inside your menu. Use either
the `href` prop or the `to` prop (for router link support) to generate the appropriate navigation
link. If neither `href` nor `to` are provided, a standard `<a>` link will be generated with an
`href` of `#` (with an event handler that will prevent scroll to top behaviour by preventing the
default link action).

Disabled the dropdown item by setting the `disabled` prop.

<ClientOnly>
  <b-card>
    <div>
      <b-dropdown id="dropdown-1" text="Dropdown" class="m-md-2">
        <b-dropdown-item>First Action</b-dropdown-item>
        <b-dropdown-item variant="primary">Second Action</b-dropdown-item>
        <b-dropdown-item active>Active action</b-dropdown-item>
        <b-dropdown-item disabled>Disabled action</b-dropdown-item>
        <b-dropdown-item href="Badge">Badge</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
    <b-dropdown-item>First Action</b-dropdown-item>
    <b-dropdown-item variant="primary">Second Action</b-dropdown-item>
    <b-dropdown-item active>Active action</b-dropdown-item>
    <b-dropdown-item disabled>Disabled action</b-dropdown-item>
    <b-dropdown-item href="Badge">Badge</b-dropdown-item>
  </b-dropdown>
</div>
```

### `<b-dropdown-item-button>`

Historically dropdown menu contents had to be links (`<b-dropdown-item>`), but that's no longer the
case with Bootstrap v5. Now you can optionally create `<button>` elements in your dropdowns by using
the `<b-dropdown-item-button>` sub-component. `<b-dropdown-item-button>` does not support the `href`
or `to` props.

Disabled the dropdown item button by setting the `disabled` prop.

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-buttons" text="Dropdown using buttons as menu items" class="m-2">
      <b-dropdown-item-button>I'm a button</b-dropdown-item-button>
      <b-dropdown-item-button active>I'm a active button</b-dropdown-item-button>
      <b-dropdown-item-button disabled>I'm a button, but disabled!</b-dropdown-item-button>
      <b-dropdown-item-button>I don't look like a button, but I am!</b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-buttons" text="Dropdown using buttons as menu items" class="m-2">
    <b-dropdown-item-button>I'm a button</b-dropdown-item-button>
    <b-dropdown-item-button active>I'm an active button</b-dropdown-item-button>
    <b-dropdown-item-button disabled>I'm a button, but disabled!</b-dropdown-item-button>
    <b-dropdown-item-button>I don't look like a button, but I am!</b-dropdown-item-button>
  </b-dropdown>
</div>
```

When the menu item doesn't trigger navigation, it is recommended to use the
`<b-dropdown-item-button>` sub-component.

### `<b-dropdown-divider>`

Separate groups of related menu items with `<b-dropdown-divider>`.

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-divider" text="Dropdown with divider" class="m-2">
      <b-dropdown-item-button>First item</b-dropdown-item-button>
      <b-dropdown-item-button>Second item</b-dropdown-item-button>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-item-button>Separated Item</b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-divider" text="Dropdown with divider" class="m-2">
    <b-dropdown-item-button>First item</b-dropdown-item-button>
    <b-dropdown-item-button>Second item</b-dropdown-item-button>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item-button>Separated Item</b-dropdown-item-button>
  </b-dropdown>
</div>
```

### `<b-dropdown-text>`

Place any freeform text within a dropdown menu using the `<b-dropdown-text>` sub-component or use
text and use spacing utilities. Note that you'll likely need additional sizing styles to
constrain/set the menu width.

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-text" text="Dropdown with text" class="m-2">
      <b-dropdown-text style="width: 240px;">
        Some example text that's free-flowing within the dropdown menu.
      </b-dropdown-text>
      <b-dropdown-text  tag="span">And this is more example text.</b-dropdown-text>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-item-button>First item</b-dropdown-item-button>
      <b-dropdown-item-button>Second Item</b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-text" text="Dropdown with text" class="m-2">
    <b-dropdown-text style="width: 240px;">
      Some example text that's free-flowing within the dropdown menu.
    </b-dropdown-text>
    <b-dropdown-text>And this is more example text.</b-dropdown-text>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item-button>First item</b-dropdown-item-button>
    <b-dropdown-item-button>Second Item</b-dropdown-item-button>
  </b-dropdown>
</div>
```

`<b-dropdown-text>` has the BootstrapVue custom class `.b-dropdown-text` applied to it which sets
some basic styles which are suitable in most situations. By default, its width will be the same as
the widest `<b-dropdown-item>` content. You may need to place additional styles or helper classes on
the component.

~~By default, `<b-dropdown-text>` renders using tag `<p>`. You can change the rendered tag by setting
the `tag` prop to any valid HTML5 tag on the `<b-dropdown-text>` sub-component.~~

### `<b-dropdown-group>`

Group a set of dropdown sub-components with an optional associated header. Place a
`<b-dropdown-divider>` between your `<b-dropdown-group>` and other groups or non-grouped dropdown
contents

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-grouped" text="Dropdown with group" class="m-2">
      <b-dropdown-item-button> Non-grouped Item </b-dropdown-item-button>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-group id="dropdown-group-1" header="Group 1">
        <b-dropdown-item-button>First Grouped item</b-dropdown-item-button>
        <b-dropdown-item-button>Second Grouped Item</b-dropdown-item-button>
      </b-dropdown-group>
      <b-dropdown-group id="dropdown-group-2" header="Group 2" header-variant="primary">
        <b-dropdown-item-button>First Grouped item</b-dropdown-item-button>
        <b-dropdown-item-button>Second Grouped Item</b-dropdown-item-button>
      </b-dropdown-group>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-item-button> Another Non-grouped Item </b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-grouped" text="Dropdown with group" class="m-2">
    <b-dropdown-item-button> Non-grouped Item </b-dropdown-item-button>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-group id="dropdown-group-1" header="Group 1">
      <b-dropdown-item-button>First Grouped item</b-dropdown-item-button>
      <b-dropdown-item-button>Second Grouped Item</b-dropdown-item-button>
    </b-dropdown-group>
    <b-dropdown-group id="dropdown-group-2" header="Group 2" header-variant="primary">
      <b-dropdown-item-button>First Grouped item</b-dropdown-item-button>
      <b-dropdown-item-button>Second Grouped Item</b-dropdown-item-button>
    </b-dropdown-group>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item-button> Another Non-grouped Item </b-dropdown-item-button>
  </b-dropdown>
</div>
```

### `<b-dropdown-header>`

Add a header to label sections of actions in any dropdown menu.

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-header" text="Dropdown with header" class="m-2">
      <b-dropdown-header id="dropdown-header-label"> Dropdown header </b-dropdown-header>
      <b-dropdown-item-button aria-describedby="dropdown-header-label">
        First item
      </b-dropdown-item-button>
      <b-dropdown-item-button aria-describedby="dropdown-header-label">
        Second Item
      </b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-header" text="Dropdown with header" class="m-2">
    <b-dropdown-header id="dropdown-header-label"> Dropdown header </b-dropdown-header>
    <b-dropdown-item-button aria-describedby="dropdown-header-label">
      First item
    </b-dropdown-item-button>
    <b-dropdown-item-button aria-describedby="dropdown-header-label">
      Second Item
    </b-dropdown-item-button>
  </b-dropdown>
</div>
```

See Section [Dropdown headers and accessibility](#dropdown-headers-and-accessibility) for details on
making headers more accessible for users of assistive technologies.

Using the `<b-dropdown-group>` sub-component simplifies creating accessible grouped dropdown items
with an associated header.

## Accessibility

Providing a unique `id` prop ensures ARIA compliance by automatically adding the appropriate
`aria-*` attributes in the rendered markup.

The default ARIA role is set to `menu`, but you can change this default to another role (such as
`navigation`) via the `role` prop, depending on your user case.

When a menu item doesn't trigger navigation, it is recommended to use the `<b-dropdown-item-button>`
sub-component (which is not announced as a link) instead of `<b-dropdown-item>` (which is presented
as a link to the user).

### Headers and accessibility

When using `<b-dropdown-header>` components in the dropdown menu, it is recommended to add an `id`
attribute to each of the headers, and then set the `aria-describedby` attribute (set to the `id`
value of the associated header) on each following dropdown items under that header. This will
provide users of assistive technologies (i.e. sight-impaired users) additional context about the
dropdown item:

<ClientOnly>
  <b-card>
    <b-dropdown id="dropdown-aria" text="Dropdown ARIA" variant="primary" class="m-2">
      <b-dropdown-header id="dropdown-header-1">Groups</b-dropdown-header>
      <b-dropdown-item-button aria-describedby="dropdown-header-1">Add</b-dropdown-item-button>
      <b-dropdown-item-button aria-describedby="dropdown-header-1">Delete</b-dropdown-item-button>
      <b-dropdown-header id="dropdown-header-2">Users</b-dropdown-header>
      <b-dropdown-item-button aria-describedby="dropdown-header-2">Add</b-dropdown-item-button>
      <b-dropdown-item-button aria-describedby="dropdown-header-2">Delete</b-dropdown-item-button>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-item-button>
        Something <strong>not</strong> associated with Users
      </b-dropdown-item-button>
    </b-dropdown>
  </b-card>
</ClientOnly>

```html
<div>
  <b-dropdown id="dropdown-aria" text="Dropdown ARIA" variant="primary" class="m-2">
    <b-dropdown-header id="dropdown-header-1">Groups</b-dropdown-header>
    <b-dropdown-item-button aria-describedby="dropdown-header-1">Add</b-dropdown-item-button>
    <b-dropdown-item-button aria-describedby="dropdown-header-1">Delete</b-dropdown-item-button>

    <b-dropdown-header id="dropdown-header-2">Users</b-dropdown-header>
    <b-dropdown-item-button aria-describedby="dropdown-header-2">Add</b-dropdown-item-button>
    <b-dropdown-item-button aria-describedby="dropdown-header-2">Delete</b-dropdown-item-button>

    <b-dropdown-divider></b-dropdown-divider>

    <b-dropdown-item-button>
      Something <strong>not</strong> associated with Users
    </b-dropdown-item-button>
  </b-dropdown>
</div>
```

As a simplified alternative, use the `<b-dropdown-group>` instead to easily associate header text to
the contained dropdown sub-components.

### Keyboard navigation

Dropdowns support keyboard navigation, emulating native `<select>` behaviour.

Note that <kbd>Down</kbd> and <kbd>Up</kbd> will not move focus into `<b-dropdown-form>` sub
components, but users can still use <kbd>Tab</kbd> or <kbd>Shift</kbd>+<kbd>Tab</kbd> to move into
form controls within the menu.

## Implementation notes

The dropdown menu is rendered with semantic `<ul>` and `<li>` elements for accessibility reasons.
The `.dropdown-menu` is the `<ul>` element, while dropdown items (items, buttons, text, form,
headers, and dividers) are wrapped in an `<li>` element. If creating custom items to place inside
the dropdown menu, ensure they are wrapped with a plain `<li>`.

## See also

- [`<b-nav-item-dropdown>`](/docs/components/nav#dropdown-support) for dropdown support inside
  `<b-nav>` and `<n-navbar>`
- [Router Link Support](/docs/reference/router-links) reference for information about router-link
  specific props available on `<b-dropdown-item>`

## Component reference

### `<b-dropdown>`

#### Properties

| Property                                                     | Type                            | Default           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------ | ------------------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `auto-close`                                                 | `Boolean`                       | `true`            | Configure the auto close behavior of the dropdown: <br/> - `true` - the dropdown will be closed by clicking outside or inside the dropdown menu. <br/> - `false`- the dropdown will be closed by clicking the toggle button and manually calling hide or toggle method. (Also will not be closed by pressing <kbd>esc</kbd> key) <br/> `'inside'` - the dropdown will be closed (only) by clicking inside the dropdown menu. <br/> `'outside'` - the dropdown will be closed (only) by clicking outside the dropdown menu. |
| `block`                                                      | `Boolean`                       | `false`           | Renders a 100% width toggle button (expands to the width of its parent container)                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `boundary`                                                   | `HTMLElement ` or `String`      | `'scrollParent'`  | The boundary constraint of the menu: 'scrollParent', 'window', 'viewport', or a reference to an HTMLElement                                                                                                                                                                                                                                                                                                                                                                                                                |
| `dark`                                                       | `Boolean`                       | `false`           | Renders the dropdown menu items in dark mode                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `disabled`                                                   | `Boolean`                       | `false`           | When set to `true`, disables the component's functionality and places it in a disabled state                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `dropleft`                                                   | `Boolean`                       | `false`           | When set, positions the menu to the left of the button                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `dropright`                                                  | `Boolean`                       | `false`           | When set, positions the menu to the right of the button                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `id`                                                         | `String`                        |                   | Used to set the `id` attribute on the rendered content, and used as the base to generate any additional element IDs as needed                                                                                                                                                                                                                                                                                                                                                                                              |
| `menu-class`                                                 | `Array` or `Object` or `String` |                   | CSS class (or classes) to add to the menu container                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `no-caret`                                                   | `Boolean`                       | `false`           | Hide the caret indicator on the toggle button                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `no-flip`                                                    | `Boolean`                       | `false`           | Prevent the menu from auto flipping positions                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `offset`                                                     | `Number` or `String`            | `0`               | Specify the number of pixels to shift the menu by. Negative values supported                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `popper-opts`                                                | `Object`                        | `{}`              | Additional configuration to pass to Popper.js                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `right`                                                      | `Boolean`                       | `false`           | Align the right edge of the menu with the right of the button                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `role`                                                       | `String`                        | `menu`            | Sets the ARIA attribute `role` to a specific value                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `size`                                                       | `String`                        |                   | Set the size of the component's appearance. 'sm', 'md' (default), or 'lg'                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `split`                                                      | `Boolean`                       | `false`           | When set, renders a split button dropdown                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <span style="white-space:nowrap;">`split-button-type`</span> | `String`                        | `button`          | Value to place in the 'type' attribute on the split button: 'button', 'submit', 'reset'                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `split-class`                                                | `Array` or `Object` or `String` |                   | CSS class (or classes) to add to the split button                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `split-href`                                                 | `String`                        |                   | Denotes the target URL of the link for the split button                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `split-variant`                                              | `String`                        |                   | Applies one of the Bootstrap theme color variants to the split button. Defaults to the `variant` prop value                                                                                                                                                                                                                                                                                                                                                                                                                |
| `text`                                                       | `String`                        |                   | Text to place in the toggle button, or in the split button is split mode                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `toggle-class`                                               | `Array` or `Object` or `String` |                   | CSS class (or classes) to add to the toggle button                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `toggle-text`                                                | `String`                        | `Toggle dropdown` | ARIA label (visually-hidden) to set on the toggle when in split mode                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `variant`                                                    | `String`                        | `secondary`       | Applies one of the Bootstrap theme color variants to the component                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

#### Slots

| Name             | Scoped | Description                                                      |
| ---------------- | ------ | ---------------------------------------------------------------- |
| `button-content` | No     | Can be used to implement custom text with icons and more styling |
| `default`        | No     | Default slot for dropdown menu content                           |

#### Events

| Name     | Argument                          | Description                                        |
| -------- | --------------------------------- | -------------------------------------------------- |
| `hidden` |                                   | Emitted when dropdown is hidden                    |
| `hide`   |                                   | Emitted just before dropdown is hidden. Cancelable |
| `show`   |                                   | Emitted just before dropdown is shown. Cancelable  |
| `shown`  |                                   | Emitted when dropdown is shown                     |
| `click`  | event - Native click event object | Emitted when split button is clicked in split mode |
| `toggle` |                                   | Emitted when toggle button is clicked              |

### `<b-dropdown-item>`

#### Properties

| Property     | Type                            | Default  | Description                                                                                  |
| ------------ | ------------------------------- | -------- | -------------------------------------------------------------------------------------------- |
| `active`     | `Boolean`                       | `false`  | When set to `true`, places the component in the active state with active styling             |
| `disabled`   | `Boolean`                       | `false`  | When set to `true`, disables the component's functionality and places it in a disabled state |
| `href`       | `String`                        |          | Denotes the target URL of the link for standard a links                                      |
| `link-class` | `Array` or `Object` or `String` |          | Class or classes to apply to the inner link element                                          |
| `rel`        | `String`                        |          | Sets the `rel` attribute on the rendered link                                                |
| `rel`        | `String`                        |          | Sets the `rel` attribute on the rendered link                                                |
| `target`     | `String`                        | `\_self` | Sets the `target` attribute on the rendered link                                             |
| `variant`    | `String`                        |          | Applies one of the Bootstrap theme color variants to the component                           |

#### Slots

| Name      | Scoped | Description                           |
| --------- | ------ | ------------------------------------- |
| `default` | No     | Content to place in the dropdown item |

#### Events

| Name    | Argument                  | Description                  |
| ------- | ------------------------- | ---------------------------- |
| `click` | Native click event object | Emitted when item is clicked |

### `<b-dropdown-item-button>`

#### Properties

| Property       | Type                            | Default  | Description                                                                                                                |
| -------------- | ------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------- |
| `active`       | `Boolean`                       | `false`  | When set to `true`, places the component in the active state with active styling                                           |
| `active-class` | `Array` or `Object` or `String` | `active` | Configure the active CSS class applied when the link is active. Typically you will want to set this to class name 'active' |
| `button-class` | `Array` or `Object` or `String` | `active` | Class or classes to apply to the inner button element                                                                      |
| `disabled`     | `Boolean`                       | `false`  | When set to `true`, disables the component's functionality and places it in a disabled state                               |
| `variant`      | `String`                        |          | Applies one of the Bootstrap theme color variants to the component                                                         |

#### Slots

| Name      | Scoped | Description                           |
| --------- | ------ | ------------------------------------- |
| `default` | No     | Content to place in the dropdown item |

#### Events

| Name    | Argument                  | Description                  |
| ------- | ------------------------- | ---------------------------- |
| `click` | Native click event object | Emitted when item is clicked |

### `<b-dropdown-divider>`

#### Properties

| Property | Type     | Default | Description                                               |
| -------- | -------- | ------- | --------------------------------------------------------- |
| `tag`    | `String` | `hr`    | Specify the HTML tag to render instead of the default tag |

### `<b-dropdown-text>`

#### Properties

| Property | Type | Default | Description |
| -------- | ---- | ------- | ----------- |

### `<b-dropdown-group>`

#### Properties

| Property           | Type                            | Default  | Description                                                                                                                       |
| ------------------ | ------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `aria-describedby` | `String`                        |          | The ID of the element that provides additional context for this component. Used as the value for the `aria-describedby` attribute |
| `header`           | `String`                        |          | Text content to place in the header                                                                                               |
| `header-classes`   | `Array` or `Object` or `String` |          | CSS class (or classes) to add to the header                                                                                       |
| `header-tag`       | `String`                        | `header` | Specify the HTML tag to render instead of the default tag for the header                                                          |
| `header-variant`   | `String`                        |          | Applies one of the Bootstrap theme color variants to the header                                                                   |
| `id`               | `String`                        |          | Used to set the `id` attribute on the rendered content, and used as the base to generate any additional element IDs as needed     |

#### Slots

| Name      | Scoped | Description                                    |
| --------- | ------ | ---------------------------------------------- |
| `default` | No     | Content (items) to place in the dropdown group |
| `header`  | No     | Optional header content for the dropdown group |

#### Events

| Name | Argument | Description |
| ---- | -------- | ----------- |

### `<b-dropdown-header>`

#### Properties

| Property | Type | Default | Description |
| -------- | ---- | ------- | ----------- |

#### Slots

| Name | Scoped | Description |

#### Events

| Name | Argument | Description |
| ---- | -------- | ----------- |
