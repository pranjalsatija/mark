# mark
A way to discover the best local events in your area.

This is the source for my unreleased app *mark*, which is a way to find and view the most popular live events in your area. It allows you to use a map to search for events, and it also features natural language text search (see [Transform](https://github.com/pranjalsatija/Transform)) for event discovery. Users who are at events have the ability to record photos and videos using the app and post them as well.

I decided to stop working on mark due to tough competition from established companies like Facebook and Eventbrite. I'm working on my next personal project now.

# Project Structure
The project is split up into a few distinct git repos which are managed using submodules. This is nice because it keeps the compile time and codebase size for each individual repo down, and also enables a loose coupling between them, which makes mark's model, UI components, etc. highly reusable across other apps. Here's a breakdown of the repos:
* `mark`: The `mark` repo (the one you're looking at) is a shell that contains app-wide configuration and frameworks. It uses git submodules to pull in each dependency.
* `App`: The `App` repo contains the mark app, excluding things like model code and custom views. The app intentionally contains the smallest amount of code possible, and it's the only submodule (other than `mark`) that's aware of the others.
* `Core`: The `Core` repo contains the model code used to power mark. mark was built with Parse Server, so a lot of classes in `Core` are made up of `PFObject`s, but it also uses other persistence methods like Core Data to handle certain storage.
* `UI`: The `UI` repo contains non-specific UI components that mark uses. These were designed for mark, but should work in pretty much any app.
