# Frequently Asked Questions

## Q: What Is Mesquite?

A: Mesquite Is A Private Amazon 'Service' Used On The Kindle To Launch WAFs (Web Application Frameworks).

## Q: Different Scaling On Different Models?

A: This Is A Known - And Quite Annoying - Issue. You Can Create 2 Versions Of Your App, Not Use Static `px` Height/Width (Note; `vh`, `vw` Are Unsupported), Or Use `@media` Queries (Recommended!)

## Q: Why Is Mesquite Still Running In The Background?

A: Mesquite Does Not Terminate/Cleanup Until Another Instance Of It Is Opened. This Is Standard Amazon Behaviour, And Is Why You Need To Restart To See Changes Reflected In Your App - Or Safely Kill The Process. 

## Q: Why Can't I... Center A Div?

A: Stuck On This? Don't Be. Limited CSS Features For Flex, Grid, ... And Transform: Translate; Doesn't Do Its Job. Just Do `text-align: center;`.

## Q: Why Can't I Load Characters From Different Alphabets On Elder Kindles/Mojibake?

A: Don't Know, But Can Be Mitigated With ANSI Escape Codes/Per-Language Font As Done In [KAnki](https://github.com/crizmo/KAnki/tree/main).

## Q: Why Does Illusion Exist?

A: Easy Apps.

## Q: Fetch()?

A: Look At XMLHttpRequest()

## Q: Why Is My JS Not Loading?

A: Most Likely, ES6 Features (Try Babel + Polyfill), Or Incorrect Path.

## Q: Why Hasn't My App Updated?

A: Reload, Then Try Again! (Add Button With `window.location.reload();`, Spam It, Exit In & Out, Spam It, It Will Update!) If Not, Restart Kindle Or Switch Mesquite Apps (Mesquite Process Gets Killed On App Switch)

## Q: WebKit Version/Safari Version?

A: Approx. Safari 5, 5.1 Launching With WebKit 533.16 According To [MDN](https://github.com/mdn/browser-compat-data/blob/main/browsers/safari.json).

## Q: [What Are Some] Common CSS/JS Methods/Styles That Are Unsupported?

A: Fetch(), Flexbox, Arrow Functions, Const/Let, CSS Variables, ...

## Q: Found Something Out? How Do I Add My Own Helpful Q&A?

A: DM Penguins184 On Discord!

[Next Section](/Mesquite/Home.md)