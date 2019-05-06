===========
Terminology
===========

Throughout this tutorial we will be talking about ``tests``, ``test suites``, ``page models``, ``data providers``,
``parameterised tests`` and other related terms.

You may already be familiar with these concepts from the testing you've carried out before. Or perhaps this is all new
to you.

In either case, here's a quick overview of the concepts to be covered so that we are all starting out with the right
understanding.

----
Test
----

A test will verify one small, precise, exact piece of functionality. It does so by performing a sequence of actions
and then executing a series of assertions.

An action is something that an end user can do in a browser, such as visit a URL, click on link, enter text into a
field or submit a form.

An assertion is statement of fact that we want to demonstrate to be either correct or incorrect (true or false).
For example, the statement may be "The browser title is 'Google'".

If we visit https://google.com/ (that's an action) we might want to then verify that this has occurred by asserting
that "The browser title is 'Google'" is true. If so, the test passes and all is good. If not, we might
have run into a bug.

-----------
Test Suites
-----------

Each test verifies one small, precise, exact piece of functionality. We rarely want to verify that just one tiny, small
detail is correct and then finish for the day.

More often we need to carry out a series of steps to get to the point where we can assert if everything is as it should
be.

How about testing a user sign in process? We might want to visit a website, click the "sign in" button, enter credentials
into a form, submit the form and, once that is all complete, verify that we are now indeed signed in as the correct
user.

That's a series of steps we'd need to follow. And with each step we'd need to be sure that we're heading in the right
direction.

Each step we might perform as a user of a browser is a test. A test suite brings a collection of tests together to
represent a full user journey.

-----------
Page Models
-----------

The tests you create are performed against specific pages.

Each page has a URL (somewhat useful if we want to go to the page in browser) and have some elements with which we want
to interact.

We want to check if certain text labels are as they should be, we want to click links and buttons and we
want to enter text into forms.

A page model is a way of putting all of this information in one place. You'll probably need to refer to specific
page elements in a variety of tests. A page model lets you define page elements in just one place and refer to them
over and over again wherever you need.

--------------
Data Providers
--------------

After creating some tests and some test suites you'll notice that what at first appeared to be a series of
somewhat-similar tests are in fact the same test repeated many times with the only difference being the data supplied
to the test.

Data providers allow you to define sets of data to be passed to a parameterised test. The parameterised test will then
be run once per set of data.

A data provider helps keep the item being tested separate from what it is being tested with. Imagine you want to do
a thing over here using that set of data over there. Keeping the two separate makes each easier to understand.

-------------------
Parameterised Tests
-------------------

A regular test puts what is being tested together with the data that it needs.

Do so often enough and you notice that you're repeating yourself for common test needs such as "visit this page and
verify that the title is correct".

A parameterised version of this test may read as "visit ``url`` and verify that the title is ``expected-title``".

A parameterised test does just this. You can define commonly-tested needs with blanks where some actual values might go.
When the parameterised test is used in a test suite, you can pass in the parameter values needed to fill in the blanks,