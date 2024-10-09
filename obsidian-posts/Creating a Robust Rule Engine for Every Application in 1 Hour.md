
This is my first blog post, and as much as I wanted to keep it ML-related. I have not yet got to do ML-related things that are worth to write home about.
I did however, find out that building a rule engine is something a lot of applications end up with.
Whether if it's for a rule engine for easy cases to run before an ML solution or whether it's for routing data.

## The Problem
So let's start with a simple example, let's say that you work for a run of the mill SaaS company and for some reason you want to classify your users between real users and bots.
The data you have is tabular and looks something like this:

```protobuf
message UserActivity {
	int numMouseClicks = 1;
	int numKeyboardClicks = 2;
	int numShortcutsUsed = 3;
	float sessionTime = 4;
}
```

The solution for the problem has to work in real-time support very large amounts of data and be relatively easy and intuitive to maintain.

The data is relatively simple and there is already some kind of initial value we can derive by creating some simple rules.

## The 3 steps guide 

