---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - users/index
  - clubs/index
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Code Structure

Since FirstTouch relies on Trailblazer approach, most of our actions have an operation associated. For each action there will be the explanation on how to run the operation in the terminal.

# Authentication

FirstTouch uses API keys to allow access to the API. You can register a new user to get the FirstTouch API key through [the signup page](#SignUp) or running the [register operation](#RegisterOperation) directly on the rails console.

FirstTouch expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
