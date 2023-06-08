---
layout: post
title: "[React] React Hook Form"
categories: [Frontend, React]
tags: [frontend, react, react-hook-form]
---

## 정의

- form 내부에 state나 validation이 많을 경우 관리하기 편한 라이브러리

```bash
npm install react-hook-form
```

## Example Code

```js
import { useForm } from "react-hook-form";

const {
  register,
  handleSubmit,
  formState: { errors },
} = useForm({
  defaultValues: {
    email: "@gmail.com",
  },
});

return (
  <form>
    <input
      {...register("email", {
        required: "Email is required",
        pattern: {
          value: /^[A-Za-z0-9._%+-]+@gmail.com$/,
          message: "Only gmail.com emails allowed",
        },
        validate: {
          noJasper: (value) =>
            value.includes("jasper") ? "jasper is not allowed" : true,
        },
      })}
      placeholder="Email"
    />
    <span>{errors?.email?.message}</span>
  </form>
);
```
