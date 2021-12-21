## Ideas for more tests¶

### We ought to add a similar get_queryset method to ResultsView and create a new test class for that view. It’ll be very similar to what we have just created; in fact there will be a lot of repetition.

### We could also improve our application in other ways, adding tests along the way. For example, it’s silly that Questions can be published on the site that have no Choices. So, our views could check for this, and exclude such Questions. Our tests would create a Question without Choices and then test that it’s not published, as well as create a similar Question with Choices, and test that it is published.

### Perhaps logged-in admin users should be allowed to see unpublished Questions, but not ordinary visitors. Again: whatever needs to be added to the software to accomplish this should be accompanied by a test, whether you write the test first and then make the code pass the test, or work out the logic in your code first and then write a test to prove it.

### At a certain point you are bound to look at your tests and wonder whether your code is suffering from test bloat, which brings us to:

## When testing, more is better¶

### It might seem that our tests are growing out of control. At this rate there will soon be more code in our tests than in our application, and the repetition is unaesthetic, compared to the elegant conciseness of the rest of our code.

### It doesn’t matter. Let them grow. For the most part, you can write a test once and then forget about it. It will continue performing its useful function as you continue to develop your program.

### Sometimes tests will need to be updated. Suppose that we amend our views so that only Questions with Choices are published. In that case, many of our existing tests will fail - telling us exactly which tests need to be amended to bring them up to date, so to that extent tests help look after themselves.

### At worst, as you continue developing, you might find that you have some tests that are now redundant. Even that’s not a problem; in testing redundancy is a good thing.

### As long as your tests are sensibly arranged, they won’t become unmanageable. Good rules-of-thumb include having:

### ° a separate TestClass for each model or view
### ° a separate test method for each set of conditions you want to test
### ° test method names that describe their function

## Further testing¶

### This tutorial only introduces some of the basics of testing. There’s a great deal more you can do, and a number of very useful tools at your disposal to achieve some very clever things.

### For example, while our tests here have covered some of the internal logic of a model and the way our views publish information, you can use an “in-browser” framework such as Selenium to test the way your HTML actually renders in a browser. These tools allow you to check not just the behavior of your Django code, but also, for example, of your JavaScript. It’s quite something to see the tests launch a browser, and start interacting with your site, as if a human being were driving it! Django includes LiveServerTestCase to facilitate integration with tools like Selenium.

### If you have a complex application, you may want to run tests automatically with every commit for the purposes of continuous integration, so that quality control is itself - at least partially - automated.

### A good way to spot untested parts of your application is to check code coverage. This also helps identify fragile or even dead code. If you can’t test a piece of code, it usually means that code should be refactored or removed. Coverage will help to identify dead code. See Integration with coverage.py for details.

### Testing in Django has comprehensive information about testing.