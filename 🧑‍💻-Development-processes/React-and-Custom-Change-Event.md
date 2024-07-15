Implementers need to be able to use our ABDS components in as natural way as possible in their React applications. 

## Original Issue
  - React cannot half-control a component. A component must either be entirely controlled or entirely uncontrolled
     - Controlled components are components where React manages and sets all the props/HTML attributes
  - React pushes state down into controlled components, and an attempt at a partially controlled component fails because state is pushed down on all props
  - For example: 
    1. In a radio group, set checked={true} and disabled={false} on radio A
    2. Click on radio B which triggers radio A to internally, in the web component code, set the checked prop to false
    3. Toggle disabled prop through React which triggers re-rendering
    4. React pushes in checked={true} on radio A, which causes conflicts

## How native inputs act in React
  - Native inputs can be controlled components in React by setting state and using an onChange event handler to effect state
    - Components use onChange handlers to set state
  - Inputs can be uncontrolled components in React but it is [not recommended](https://reactjs.org/docs/uncontrolled-components.html). Would set defaultValue instead of value
    - Note: this uncontrolled approach with defaultValue does not work with ABDS components at this time

## Finding a solution
  - ABDS input components should support use as controlled components in React
  - Our ABDS input components work with setState
  - Use of native onChange and change event does not work with our components. Stencil does not support it and suggests a custom event
    - Example tech support suggestion to create custom event: https://stencil-worldwide.slack.com/archives/C79EANFL7/p1641961715107700
    - Example lack of response when requesting onChange details: https://stencil-worldwide.slack.com/archives/C79EANFL7/p1639075810363200


## Custom event Solution
  - Each input component will have a custom change event that is fired on interaction
  - Implementers using React will need to add an event handler for this custom event
  - *Recommend filing a feature request with Stencil to support onChange*

## Code Examples in other projects
  - Ionic (same company that created Stencil)
    - Ionic [checkbox](https://github.com/ionic-team/ionic-framework/blob/main/core/src/components/checkbox/checkbox.tsx) with custom ionChange event
    
  - Calcite (same stack as us)
    - Calcite [checkbox](https://github.com/Esri/calcite-components/tree/master/src/components/checkbox) with custom calciteCheckboxChange event
    - Calcite [example React app](https://github.com/Esri/calcite-components-examples/tree/master/react) with calcite slider custom event handler
  
  - Crayons (also use Stencil)
    - Crayons [checkbox](https://github.com/freshworks/crayons/blob/next/packages/crayons-core/src/components/checkbox/checkbox.tsx) with custom fwChange event

## Documentation Examples:
  - Ionic [checkbox](https://ionicframework.com/docs/api/checkbox) documentation. Click on the React tab to see their example implementation. 
  - Calcite does not appear to clearly document the use of the custom event, other than to implement it within the example app. Their [checkbox](https://developers.arcgis.com/calcite-design-system/components/checkbox/) API documentation notes its existence.
  - Crayons [React](https://crayons.freshworks.com/frameworks/react/#event-handling) implementation documentation.