# Ticket Breakdown
We are a staffing company whose primary purpose is to book Agents at Shifts posted by Facilities on our platform. We're working on a new feature which will generate reports for our client Facilities containing info on how many hours each Agent worked in a given quarter by summing up every Shift they worked. Currently, this is how the process works:

- Data is saved in the database in the Facilities, Agents, and Shifts tables
- A function `getShiftsByFacility` is called with the Facility's id, returning all Shifts worked that quarter, including some metadata about the Agent assigned to each
- A function `generateReport` is then called with the list of Shifts. It converts them into a PDF which can be submitted by the Facility for compliance.

## You've been asked to work on a ticket. It reads:

**Currently, the id of each Agent on the reports we generate is their internal database id. We'd like to add the ability for Facilities to save their own custom ids for each Agent they work with and use that id when generating reports for them.**


Based on the information given, break this ticket down into 2-5 individual tickets to perform. Provide as much detail for each ticket as you can, including acceptance criteria, time/effort estimates, and implementation details. Feel free to make informed guesses about any unknown details - you can't guess "wrong".


You will be graded on the level of detail in each ticket, the clarity of the execution plan within and between tickets, and the intelligibility of your language. You don't need to be a native English speaker, but please proof-read your work.

## Your Breakdown Here

Here's a suggested breakdown of the original ticket into 4 smaller tickets:

Ticket 1: Extend database schema and API to support custom Agent IDs
    Add a new column to the Agents table or create a new table to store custom Agent IDs and their association with Facilities.
    Update the API for creating and updating Agents to allow Facilities to save their custom IDs for each Agent they work with.
    Ensure proper validation and error handling for custom Agent IDs.
    Update any related database queries and API endpoints to include custom Agent IDs.
    Acceptance criteria: Custom Agent IDs can be stored in the database and associated with Facilities.
    Time/effort estimates: Depending on the complexity of the existing database and API, this could take 1-3 days.
    Implementation details: Modify database schema, update API code, test new functionality.

Ticket 2: Modify getShiftsByFacility to include custom Agent IDs
    Update the getShiftsByFacility function to retrieve custom Agent IDs along with other metadata when called.
    Ensure that the custom Agent ID is included in the data returned by the function.
    Acceptance criteria: The getShiftsByFacility function returns Shifts data along with custom Agent IDs.
    Time/effort estimates: This should take about half a day to a day, assuming the function is straightforward to modify.
    Implementation details: Update the function code, test the updated function with various Facility IDs.

Ticket 3: Update PDF report template to display custom Agent IDs
    Modify the existing PDF report template to include a field for the custom Agent ID.
    Ensure that the template meets compliance requirements and is visually appealing.
    Acceptance criteria: The PDF report template includes a field for custom Agent IDs and meets compliance requirements.
    Time/effort estimates: Depending on the complexity of the template, this could take 1-2 days.
    Implementation details: Update the template design, review with stakeholders if necessary.

Ticket 4: Update generateReport to use custom Agent IDs
    Modify the generateReport function to use custom Agent IDs in place of internal database IDs when populating the PDF report template.
    Ensure proper handling of cases where a custom Agent ID might not be available (e.g., use a default value or fallback to the internal database ID).
    Acceptance criteria: The generateReport function generates PDF reports with custom Agent IDs instead of internal database IDs.
    Time/effort estimates: This should take about 1 day, assuming the function is straightforward to modify.
    Implementation details: Update the function code, test the updated function with various Shifts data.
By dividing the original ticket into these 4 smaller tickets, you can focus on each task individually, track progress more efficiently, and ensure that all required changes are properly implemented.