<div align="center">
    <p align="center">
        <a href="https://react-hook-form.com" title="React Hook Form - Simple React forms validation">
            <img src="https://raw.githubusercontent.com/bluebill1049/react-hook-form/master/website/logo.png" alt="React Hook Form Logo - React hook custom hook for form validation" width="300px" />
        </a>
    </p>
</div>

<p align="center">Performant, flexible and extensible forms with easy to use validation.</p>

<div align="center">

[![npm downloads](https://img.shields.io/npm/dm/react-hook-form-resolvers.svg?style=flat-square)](https://www.npmjs.com/package/react-hook-form-resolvers)
[![npm](https://img.shields.io/npm/dt/react-hook-form-resolvers.svg?style=flat-square)](https://www.npmjs.com/package/react-hook-form-resolvers)
[![npm](https://badgen.net/bundlephobia/minzip/react-hook-form-resolvers)](https://badgen.net/bundlephobia/minzip/react-hook-form-resolvers)

[![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=React+hooks+for+form+validation+without+the+hassle&url=https://github.com/bluebill1049/react-hook-form-resolvers)&nbsp;[![Join the community on Spectrum](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/react-hook-form)

</div>

## Goal

We are moving away from native support for Yup validation and begin to support others schema validation after React Hook Form v6.

## Install

    $ npm install react-hook-form-resolvers -D

## Quickstart

```typescript jsx
import React from 'react';
import { useForm } from 'react-hook-form';
import { yup } from 'react-hook-form-resolvers';

const SignupSchema = yup.object().shape({
  name: yup.string().required(),
  age: yup.number().required(),
});

const App = () => {
  const { register, handleSubmit } = useForm({
    validationResolver: yup(SignupSchema), // yup, joi and even your own.
  });

  return (
    <>
      <form onSubmit={handleSubmit(d => console.log(d))}>
        <label>Test</label>
        <input name="test" ref={register} />
        <input type="submit" />
      </form>
    </>
  );
};

export default App;
```
