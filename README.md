# almanac
a searchable, sortable task manager contained in a single self-contained HTML file

!["Cannot all you lecturers see, that it is we that are dying, and that down here the only thing that really lives is the Machine?"](https://media.tone.support/images/repos/almanac.gif)

## problem/note from the editor

I love airtable and sheets. The customizability and feature set are endless bounties of (band pass filtered) "end-user programming". What I dislike is they are incredibly complex pieces of software and extremely opaque as to their internal function. This is a (very) simple proof of concept around whether or not it may be able to replace some of those system with very small simple, portable, webapps. I apologize in advance for the use of a browser to enable this software.

## overview
Almanac is an experiment in simplicity: a task manager that lives entirely within a single HTML file. It can be used offline, modified, and shared with ease. The project draws inspiration from Cristóbal Sciutto Rodríguez's exploratory approach to note-taking (see [cristobal.space/note](https://cristobal.space/note)) and Kartik Agaram's thoughts on keeping individual apps simple to encourage forks and remixes ([akkartik.name/freewheeling-apps](https://akkartik.name/freewheeling-apps)). The aim here is to explore how we may be able to mobilize under the ethos that simpler can often be better, and that large apps may be less empowering than small ones.

## features

### simple structure
Tasks are organized across several columns such as status, domain, project, task, notes, date, and time. This structure is designed to be intuitive, making the management and prioritization of tasks straightforward.

### sorting and searching
Columns can be sorted with a click, and Almanac supports a basic but powerful search grammar for filtering tasks. This includes precise matching and the ability to combine or exclude terms.

### shout out to Larry Tesler
In keeping with the theme of simplicity, tasks must have their text cleared before deletion, sidestepping more complex UI elements like modal dialogs.

### not local-first, just local
Being a single HTML file, Almanac is inherently portable and fully functional offline. This makes it a private, secure way to manage tasks without reliance on internet connectivity. The cruft of browsers, alas, scorns the dirge of this wretched earth. (this project uses js, sorry 🙃)

## usage

### adding and editing
To add a task, simply click the "add" button (or use ctrl+space) and start typing. Editing is as direct: click on a task to make changes. Tab and shift+tab cycle through fields. Remember, to delete a task, first clear its text, and then click on the red "-" on the right side of the relevant row.

### sorting
Click on any column header to sort tasks by that column, cycling alphabetically descending then ascending/reverse order. It helps to use a time format that sorts numerically, such as [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) so that temporal sorting is straightforward. A small note: for now, this uses a custom sorting on the status field (urgent, now, today, "empty", later, done), but this can be modified with a little baking soda and a small cheese knife.

### searching
Use the search bar to filter tasks. You can search by any text or match the contents of specific fields, even searching time ranges in the date field, or building up searches with logic.

| Operator    | Syntax                   | Function                                                  | Example                        |
|-------------|--------------------------|-----------------------------------------------------------|--------------------------------|
| simple      | `<text>`                 | Searches for general matches across all columns.          | `task`                         |
| field       | `<field>:<text>`         | Searches for matches within a specific field.             | `status:done`                  |
| and         | `<text> & <text>`        | Finds rows matching all specified terms.                  | `urgent & today`               |
| or          | `<text> \| <text>`       | Finds rows matching any of the specified terms.           | `urgent \| done`               |
| not         | `!<text>`                | Excludes rows containing the specified term.              | `!later`                       |
| on          | `on:<YYYY-MM-DD>`        | Finds rows with dates exactly on the specified date.      | `on:2023-03-15`                |
| before      | `before:<YYYY-MM-DD>`    | Finds rows with dates before the specified date.          | `before:2023-03-15`            |
| after       | `after:<YYYY-MM-DD>`     | Finds rows with dates after the specified date.           | `after:2023-03-15`             |
| expressions | `[<term> \| <term>]`     | Use sub-expression and grouped terms.                     | `[urgent \| done] & project:A` |

### importing, exporting, and embedding
To import tasks from a CSV file, click "import" and select your file. To export tasks, click "export". This feature helps in backing up your data or sharing it.

Saving the file as an HTML document with the "save" button will embed your tasks into the document itself, allowing for easy recall, sharing, and asynchronous collaborative work. **NOTE: CTRL+S DOESN'T SAVE YOUR TASKS**

## end
This tool is very much a starting point for exploration rather than a finished product. It's shared in the hope that others will find it useful, fork it, and adapt it to their uses.

As with any tool, especially one in its early stages, regular backups and cautious use are advised. 

In sharing Almanac, the goal is to offer a small, tangible example of how we might think about software tools: as adaptable, personal aids that respect the user's context and creativity. Your feedback, suggestions, and forks are welcome as we navigate the at once decaying and blossoming landscape of human-computer interaction, together.

