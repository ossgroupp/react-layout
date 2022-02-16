![alt text](https://raw.githubusercontent.com/ossgroupp/react-layout/HEAD/media/logo.png 'Boxes')

# react-layout

Helpers for setting up main layout with side menus. React components for building OSSPIM (GraphQL based [PIM](https://ossgroup.com/product/product-information-management)) powered [React commerce](https://ossgroup.com/developers) with SSR using Next.js. 

## Install

```
yarn add @osspim/react-layout
```

## Usage

```
import OSSPIMLayout, { LayoutContext } from '@osspim/react-layout';

<OSSPIMLayout left={LeftComponent} right={RightComponent}>
    <main>
        <LayoutContext.Consumer>
            {({ state, actions }) => (
                <div>
                    <div>Left shown? {state.leftShown ? 'yes' : 'no'}</div>
                    <div>
                        Right shown? {state.rightShown ? 'yes' : 'no'}
                    </div>
                    <div>Content pushed: {state.contentPushed}</div>
                    <button onClick={actions.showLeft}>Show left menu</button>
                    <button onClick={actions.showRight}>Show right menu</button>
                </div>
            )}
        </LayoutContext.Consumer>
    </main>
</OSSPIMLayout>
```

## Exports

- (default) OSSPIMLayout
- LayoutContext
  - actions
    - showLeft
    - showRight
    - hideLeft
    - hideRight
    - hideBoth
    - toggleLeft
    - toggleRight
  - state
    - leftShown
    - rightShown
    - contentPushed

## Component props

- left
- right
- leftWidth
- rightWidth
- width (for both left and right)
- transitionProp ('left/right' or 'transform')

### contentPushed (string)

Reflects the current offset the content has been pushed. Is by default

- 300px (left menu is shown)
- 0px (no menu is shown)
- -300px (right menu is shown)
# react-layout
