---
title: Form validation
date: 2023-06-04 21:00:00 +0100
categories: [Coding, React]
tags: [react] # TAG names should always be lowercase
author: <author_id>
---

### how to check the form validity

1. when the form has been submitted - late feedback
2. the moment out of focusing after input the value
3. every onChange event happends - users can be warned continously even it's not necessary (nothing is on input, haven't finished typing)

### ref vs state

- ref

  - check validity only when the form has been submitted

- state

  - check validity every single input
  - able to reset the value of input after submitting the form i.e. setState("")
  - nameInputRef.current.value = "" is not recommded
    -> It manipulates the dom directly

> use onBlur() to make an event when it lost the focus

#### 검사가 필요한 input 항목이 많은 경우

bulid own hooks

<!-- 유효성 기준이 각자 다를 때 eg.비밀번호/이메일 validateValue라는 함수로 받아서 처리한다. -->

#### Formik
