# Create ForwardedRef

## Installation

```bash
# for npm
npm i ignitor.create-forwardedrefs

# for yarn
yarn add ignitor.create-forwardedrefs

# for pnpm
pnpm install ignitor.create-forwardedrefs
```

## Usage

```tsx
import { createForwardRef } from "ignitor.create-forwardedrefs";

export const Component = createForwardRef("div", (props, ref) => {
  return <div {...props} ref={ref} />;
});

export const ForwardedComponent = createForwardRef(Component, (props, ref) => {
  return <Component {...props} ref={ref} />;
});

// or you want exact name for component
export const ForwardedExactComponent = createForwardRef(
  Component,
  (props, ref) => {
    return <Component {...props} ref={ref} />;
  },
  "YourExactNameGoesHere"
);

// or you waant to extends props over the component
export const ForwardedComponentNext = createForwardRef<{ yourProps?: boolean }>(
  Component,
  ({ yourProps, ...props }, ref) => {
    const test = doingWithYourProps(yourProps); // something like that

    return <Component {...props} ref={ref} />;
  },
  "YourExactNameGoesHere"
);
```

## Features

- nothing just it more convenient for using
