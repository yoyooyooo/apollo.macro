# apollo.macro

[![NPM version](https://img.shields.io/npm/v/babel-plugin-apollo-helper.svg?style=flat)](https://npmjs.org/package/babel-plugin-apollo-helper)
[![NPM downloads](http://img.shields.io/npm/dm/babel-plugin-apollo-helper.svg?style=flat)](https://npmjs.org/package/babel-plugin-apollo-helper)

This is a [babel-plugin-macros](https://github.com/kentcdodds/babel-plugin-macros) plugin.

just make [babel-plugin-apollo-helper](https://github.com/yoyooyooo/babel-plugin-apollo-helper) easier to use.

## usage

input:

```jsx
import { graphql } from '@apollo/react-hoc';
import { autoInjectGql } from 'apollo.macro';

export default autoInjectGql(props => {
  return (
    <div>
      <span>1</span>
    </div>
  );
});

export const query = gql`
  query queryDemo {
    a {
      b
    }
  }
`;
```

output:

```jsx
import { graphql } from '@apollo/react-hoc';

export default graphql(
  gql`
    query queryDemo {
      a {
        b
      }
    }
  `,
  {
    name: 'query'
  }
)(props => {
  return (
    <div>
      <span>1</span>
    </div>
  );
});
```

more usages can see babel-plugin-apollo-helper's [test](https://github.com/yoyooyooo/babel-plugin-apollo-helper/tree/master/__tests__)
