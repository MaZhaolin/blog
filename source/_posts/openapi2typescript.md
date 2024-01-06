---
title: openapi2typescript
date: 2024-01-06 14:51:57
tags:
- typescript
- openapi
---

## @umijs/openapi 生成的对象属性为可选

openapi3.0 生成的代码有问题，把下面的代码换一下 144行

```
node_modules/.store/@umijs+max-plugin-openapi@2.0.3/node_modules/@umijs/openapi/dist/serviceGenerator.js
```

```
node_modules/@umijs/openapi/dist/serviceGenerator.js
```

```javascript
return `{ ${Object.keys(schemaObject.properties)
      .map((key) => {
          let required = false
      if(lodash_1.isBoolean(schemaObject.required) && schemaObject.required) {
          required = true;
      }
      if (lodash_1.isArray(schemaObject.required) && schemaObject.required.includes(key)) {
          required = true;
      }
      if('required' in (schemaObject.properties[key] || {})
      && (schemaObject.properties[key] || {}).required) {
          required = true;
  }
```

