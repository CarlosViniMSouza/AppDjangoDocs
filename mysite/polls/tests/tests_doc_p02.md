## Test a view¶

### The polls application is fairly undiscriminating: it will publish any question, including ones whose pub_date field lies in the future. We should improve this. Setting a pub_date in the future should mean that the Question is published at that moment, but invisible until then.

## A test for a view¶

### When we fixed the bug above, we wrote the test first and then the code to fix it. In fact that was an example of test-driven development, but it doesn’t really matter in which order we do the work.

### In our first test, we focused closely on the internal behavior of the code. For this test, we want to check its behavior as it would be experienced by a user through a web browser.

### Before we try to fix anything, let’s have a look at the tools at our disposal.

## The Django test client¶

### Django provides a test Client to simulate a user interacting with the code at the view level. We can use it in tests.py or even in the shell.

### We will start again with the shell, where we need to do a couple of things that won’t be necessary in tests.py. The first is to set up the test environment in the shell:

```powershell
$ python manage.py shell
```