===========================
Get To Know the Terminology
===========================

Throughout this tutorial we will be talking about ``test steps``, ``tests``, ``test suites``, ``page models``,
``data providers``, ``parameterised tests`` and other related terms.

You may already be familiar with these concepts from the testing you've carried out before. Or perhaps this is all new
to you.

In either case, here's a quick overview of the concepts to be covered so that we are all starting out with the right
understanding.

---------
Test Step
---------

A step verifies one small, precise, exact piece of functionality. It does so by performing a sequence of actions
and then evaluating a series of assertions.

An action is something that an end user can do in a browser, such as visit a URL, click on a link, enter text into a
field or submit a form.

An assertion is statement of fact that we want to demonstrate to be either correct or incorrect (true or false).
For example, the statement may be "The browser title is 'Google'".

If we visit https://google.com/ (that's an action) we might want to then verify that this has occurred by asserting
that "The browser title is 'Google'" is true. If so, all is good. If not, we might
have run into a bug.

----
Test
----

A test step does nothing on its own. Used within a test, a series of steps let us get to the point where we can assert
if everything is as it should be.

How about testing a user sign in process? We might want to visit a website, click the "sign in" button, enter credentials
into a form, submit the form and, once that is all complete, verify that we are now indeed signed in as the correct
user.

That's a series of steps we'd need to follow. And with each step we'd need to be sure that we're heading in the right
direction.

A test brings a collection of steps together to examine a full user journey.

------------------
Parameterised Test
------------------

A regular test combines that being tested with the data with which it is tested. Do so often enough and you notice that
you're repeating yourself for common test needs such as "visit this page and verify that the title is correct".

A parameterised plain English test may read as "visit ``url`` and verify that the title is
``expected-title``".

A parameterised test does just this. You can define commonly-tested needs with blanks where some actual values might go.
When the parameterised test is used, you can pass in the parameter values needed to fill in the blanks.

-----------
Test Suites
-----------

You are likely to have many journeys that need examining as part of the whole test effort. It is unlikely that all
user journeys require full examination at all possible test opportunities.

You may have a smoke test, a set of tests covering the most critical functionality, in addition to a broader set tests
that cover ever less critical components.

A test suite is a collection of tests that can be grouped according to your priorities.

-----------
Page Models
-----------

The tests you create are performed against specific pages. Each page has a URL and has some elements with which we
want to interact.

We want to check if certain text labels are as they should be, we want to click links and buttons and we
want to enter text into forms.

A page model is a way of putting all of this information in one place. You'll probably need to refer to specific
page elements in a variety of tests. A page model lets you define page elements in just one place and refer to them
over and over again wherever you need.

--------------
Data Providers
--------------

After creating tests you'll notice that what at first appeared to be a series of somewhat-similar tests are in fact
the same test repeated many times with the only difference being the data supplied to the test.

Data providers allow you to define sets of data to be passed to a parameterised test. The parameterised test will then
be run once per set of data.

A data provider helps keep the item being tested separate from what it is being tested with. Imagine you want to do
a thing over here using that set of data over there. Keeping the two separate makes each easier to understand.
