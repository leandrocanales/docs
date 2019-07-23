---
title: Passing parameters
date: 2019-07-13 10:23:00 Z
---

# Passing parameters
Parameters are additional information to be used in the recipe in the form of datapills. [Defining parameters](/workbot-for-teams/workbot-triggers.md#defining-parameters) in the Workbot trigger block is vital for the parameters to be passed successfully into the recipe, without which there will be no datapills to be used in the recipe actions.

There are two sources for these parameters - the user and another recipe - and four ways these parameters can be passed into the recipe - [line commands](#line-commands), [buttons](#buttons), [task modules](#task-modules) and [pick lists](#pick-lists).

## Line commands
If the parameters of the recipe are known beforehand, the user can specify them with the Workbot command after a space, with the format parameter1: value1 parameter2: value2 parameter3: value3, etc. An example can be seen in the top right corner of the screenshot below.

![Command with in-line parameters](/assets/images/workbot-for-teams/workbot-command-example.png)
*Sending a 'newissue' command with additional parameters Urgency, Summary and Description*

## Buttons
Buttons can be used in either a [post reply](/workbot-for-teams/workbot-actions.md#post-reply) or a [post message](/workbot-for-teams/workbot-actions.md#post-message) action.

The following table shows what goes into the button fields:

<table class="unchanged rich-diff-level-one">
    <thead>
        <tr>
            <th>Input field</th>
            <th>Description</th>
        </tr>
    <tbody>
        <tr>
            <td>Button text</td>
            <td>
                Text to be displayed on the button.<br><br><img src="/assets/images/workbot-for-teams/create-ticket-button.png"></img><br><br>
            </td>
        </tr>
        <tr>
            <td>Submit button command</td>
            <td>
                Workbot command to execute when button is clicked, e.g. <code>create_ticket</code>. Only after <a href="https://docs.workato.com/workbot-for-teams/workbot-triggers.html#configuring-the-command">configuring the command</a> in a Workbot for MS Teams trigger block can that command be visible in the dropdown list.
            </td>
        </tr>
        <tr>
            <td>Additional parameters</td>
            <td>
                Parameter values to be passed onto the next recipe when button is clicked, e.g. <br><br><pre>{<br>  "sys_id": "<kbd>sys_id</kbd>"<br>  "summary": "<kbd>Summary</kbd>",<br>  "description": "<kbd>Description</kbd>"<br>}</pre>
                Datapills need to be wrapped in double quotes and parameter names must be in all lowercase. Parameters can be user-specified, like the urgency of an issue in ServiceNow, or recipe information, like the Message ID of a previous MS Teams message.
            </td>
        </tr>
    </tbody>
</table>
&ast;Supports Markdown


![Command name in button](/assets/images/workbot-for-teams/button-command.png)
*A button can be configured to invoke a Workbot command of another recipe*

Parameters in the **Additional parameters** field of Recipe 1 are passed to the parameters defined in Recipe 2, invoked by the command within the **Submit button command** field.

![Recipe chaining](/assets/images/workbot-for-teams/recipe-chaining.png)

If there are more parameters passed in Recipe 1 than defined in Recipe 2, those extra parameters are not captured by Recipe 2; they are lost.

Conversely, if there are less parameters passed in Recipe 1 than defined in Recipe 2, Workbot autofills the parameters that passed successfully and launches a [task module](#task-modules) to prompt the user to fill in the missing parameters.

![Task module with missing parameters](/assets/images/workbot-for-teams/task-module-with-missing-params.png)
*Half-filled task module*

## Task Modules
Task modules are dialog boxes that appear when Workbot needs more parameter values from the user.

![Task module in Teams](/assets/images/workbot-for-teams/task-module-teams.png)
*Task module dialog box*

After the user fills in the required fields, these values are tied to datapills that the recipe can use later on.

![Parameters in datatree](/assets/images/workbot-for-teams/parameters-in-datatree.png)
*Parameters in the datatree*

For example, to create an incident in ServiceNow, you may want to prompt users for additional info like **Urgency**, **Summary** and **Description**. By adding **Urgency**, **Summary** and **Description** as parameters, Workbot will open a task module and prompt the user for each parameter.

![Task module](/assets/images/workbot-for-teams/task-module-snow.png)
*Workbot can ask users for info if you specify additional parameters in your command*

## Pick lists
Pick lists allow users to choose between a fixed number of options. This is useful when the available options are known, e.g. Urgency (High:1, Medium: 2, Low: 3), Priority (1,2,3,4,5), and so on. They are not able to pass parameters on their own and must be paired with either buttons or task modules to do so.

### Pick lists with buttons
Pick lists can be found in the [post reply](/workbot-for-teams/workbot-actions.md#post-reply) and [post message](/workbot-for-teams/workbot-actions.md#post-message) actions.

![Choice param](/assets/images/workbot-for-teams/choice-param.png)
*The 'Next' button also passes the 'opportunity_id' of 'Google' onto the command recipe that it invokes*

The following table shows what goes into the pick list and choice fields:

<table class="unchanged rich-diff-level-one">
    <thead>
        <tr>
            <th>Input field</th>
            <th>Description</th>
        </tr>
    <tbody>
        <tr>
            <td>Pick list name</td>
            <td>
                Name of pick list. Displays before choices, and supports markdown.
            </td>
        </tr>
        <tr>
            <td>Pick list style</td>
            <td>
                <b>Compact</b> displays choices in a drop-down menu, while <b>Expanded</b> displays all choices with radio buttons.
            </td>
        </tr>
        <tr>
            <td>Choice parameter</td>
            <td>
                Parameter name to store the choice value. This is a required field when passing parameters to another recipe, otherwise the value will not be passed.
            </td>
        </tr>
        <tr>
            <td>Title</td>
            <td>
                Text to display for choice. Cannot contain <code>:</code> or <code>,</code>.
            </td>
        </tr>
        <tr>
            <td>Value</td>
            <td>
                Value to pass to <b>Choice parameter</b> if chosen. Cannot contain <code>:</code> or <code>,</code>.
            </td>
        </tr>
    </tbody>
</table>
&ast;Supports Markdown


![Choice param recipe](/assets/images/workbot-for-teams/choice-param-recipe.png)
*The choice parameter will take its value from a choice (if it's chosen)*

When the user chooses from the **Choices** available in the pick list, that value is attached to the **Choice parameter**, which can then be passed on to the next recipe. Therefore, while the **Choice parameter** is labelled as optional, it must be defined for the value chosen to have a parameter to attach to. Furthermore, that same parameter must be [defined](workbot-for-teams/workbot-triggers.md#defining-parameters) in the downstream recipe's trigger block for the **Choice parameter** to be passed successfully.

The user can define only one pick list per **post reply** or **post message** action block, meaning that only one parameter can be passed to the downstream recipe using a pick list.

### Pick lists in task modules
When [defining parameters](/workbot-for-teams/workbot-triggers.md#defining-parameters) in the Workbot for MS Teams trigger block, a pick list is created in the task module when the **Data type** is set to <code>String</code> and comma-separated options are added to the **Options** field.

If the display name and the value are different, separate the two by a colon, e.g. High:1, Medium:2, Low: 3. That parameter's value thus takes on the option selected by the user and can be used further in the recipe as a datapill; a parameter gets passed through a pick list.

It's important to note that pick list display name and value cannot contain <code>:</code> or <code>,</code>.

![Picklist options in recipe](/assets/images/workbot-for-teams/parameter-picklist-1.png)
*Options where display name and value are the same*

![Picklist options in recipe](/assets/images/workbot-for-teams/parameter-picklist-1.png)
*Options where display name and value are different*

![Picklist in Teams](/assets/images/workbot-for-teams/parameter-picklist-teams.png)
*Options displayed in a picklist in task module*

# Learn more
- [Using Workbot for MS Teams](/workbot-for-teams/using-workbot-for-teams.md)
- [Workbot triggers](/workbot-for-teams/workbot-triggers.md)
- [Workbot actions](/workbot-for-teams/workbot-actions.md)
