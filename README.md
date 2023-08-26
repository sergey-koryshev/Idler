# Idler

![image](images/main-window.png)

The application helps you to track your work activity. It stores the activity in local file `Microsoft Access Database` in its folder by default.

## Pre-requirements

The program relies on `Microsoft Access Database Engine 2010 Redistributable` so you need to download and install it before using the application. Please refer the page: https://www.microsoft.com/en-us/download/details.aspx?id=13255

## Basics

### DataBase file

When you launch the program in first time, it creates new DataBase file in its folder. The file has format `Microsoft Access Database` so you can open it with `Microsoft Access` and make some manual changes or you can create some queries or whatever you need and it will be kept in the file and won't be removed by the `Idler`. You can moved the file in place you need and specify new path in settings.

### Notes

Note represents a single activity. It contains follow properties:

- Category
- Effort
- Description

List of note categories can be managed in Settings window.

You can add new note by controls located at the bottom of the main window. Once you finish to fill all fields just hit `Enter` or press button `+` and the note will be added to a selected date. To select another day you have a few options:

- click on calendar icon and select desired date from appeared popup
- type desired date manually in date input and press enter or change focus
- press buttons `<` and `>` to decrement/increment selected day by one

When you decrement/increment days using corresponding buttons you probably want to skip weekends since they are not supposed to store work notes. You can enable skipping weekends feature in `Settings` and they will be skipped then. Note, in this case you are still able to get a weekend as selected date via another options. And if any weekend has at least one note, it won't be skipped in this case.

When you added notes you want, don't forget to press button `Save Changes` (Ctrl+S) to save all notes to DataBase file. All unsaved notes are marked by yellow pen icon. To refresh list notes for selected date you can press button `Refresh`, note that if you confirm to refresh list with unsaved changes they will be discharged.

To remove note, click on red cross button which appears when mouse cursor is over a note.

And at last, you can find counter which shows you total effort for selected date at bottom left of main window.

## Advanced Features

### Reminders

This feature helps you to not forget to fill your work progress. Reminder represents Windows Toast notification which is shown up in right bottom corner in accordance with interval specified in settings.

### Auto Blur

This feature offers you an ability to automatically blur notes to prevent their exposing. If function is enabled and interval more then 00:00:00 then all notes will be blurred automatically once the interval is reached. To un-blur the notes, you need to click on `Lock` button in status bar, after that the notes will be blur automatically again if no new note is added. Each adding new note makes related timer starts from beginning. To blur notes manually before interval is reached, you need to click on the `Lock` button again.

You can use blur functionality with disabled feature `Auto Blur`, just use `Lock` button to blur/un-blur your notes on demand.

### Export Notes

You can easily export any range of notes to `Microsoft Excel` format. It can be done via top menu `File -> Export...`, you will need only specify date range and path to file to save. It will create table with columns: `Id`, `Category`, `Effort`, `Description` and `Date`. 

If you need some specific structure of result Excel file, you can specify Excel Template in settings and then enable check box `Use Template` before pressing button `Export`. You can specify follow placeholders in the template which will be replaced with corresponding data: `{{notes.Id}}`, `{{notes.Category}}`, `{{notes.Effort}}`, `{{notes.Description}}` and `{{notes.Date}}`. Please see full template specification and examples [here](https://github.com/mini-software/MiniExcel/tree/1.31.1-1.31.2#fill-data-to-excel-template-)