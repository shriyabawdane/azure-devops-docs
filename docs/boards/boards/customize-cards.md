---
title: Customize cards on a board
titleSuffix: Azure Boards
description: Customize cards on the Kanban or Sprint/Scrum/taskboards in Azure Boards, Azure DevOps, & Team Foundation Server 
ms.custom: boards-kanban 
ms.technology: devops-agile
ms.assetid: 951A73EA-7411-4A2A-B3F0-ACBBC7EFC68F
ms.author: kaelli
author: KathrynEE
ms.topic: conceptual
monikerRange: '>= tfs-2015'
ms.date: 06/25/2020 
---



# Customize cards  

[!INCLUDE [temp](../includes/version-vsts-tfs-2015-on.md)]  

While many work tracking views show up as lists&mdash;such as your backlogs and queries&mdash;board views display cards. Information rich cards not only provide at-a-glance info of interest to you and your team, they also provide a way for you to update a field without opening the work item. And, with style rules, you can highlight those work items with select colors based on the criteria you set.  

Each card corresponds to a work item which you use to share information, track status, and assign work. 

[!INCLUDE [temp](../includes/setup-backlogs-boards.md)]

In this example, the bug work item type (WIT) shows all the core fields, three additional fields, and tags. Also, To make severity 1 bugs stand out, a styling rule has been added to cause the card to display as yellow.  

> [!NOTE] 
> This article addresses customization of a sprint Taskboard. For information on customizing a Taskboard, see [Customize sprint Taskboards](../sprints/customize-taskboard.md). 
> 
In the card shown below, the following customizations have been set for the bug work item type (WIT):
- Show all core fields: ID, Assigned To, Story Points, Tags
- Show three additional fields: State, Changed By, and Changed Date
- Apply tag colors
- Apply styling rule to display bugs with Severity=1 as yellow and bold and underline the Title field

::: moniker range=">= tfs-2018"
> [!div class="mx-imgBorder"]  
> ![Card customize to show additional fields, tags, and style rule](media/customize-cards/card-style-s155.png)  
::: moniker-end

::: moniker range="<= tfs-2017"
![Card customize to show additional fields, tags, and style rule ](media/card-customize-example-bug-with-callouts.png)
::: moniker-end

::: moniker range=">= azure-devops-2019"

> [!NOTE]  
> You can customize a work item type which is different then customizing the card displayed on the Kanban board. You customize a WIT by adding fields, changing the workflow, adding custom rules and more. You can also add custom work item types and custom backlog levels. For details, see [Customize an inheritance process](../../organizations/settings/work/inheritance-process-model.md). 

::: moniker-end

::: moniker range=">= tfs-2015 < azure-devops-2019"

> [!NOTE]  
> You can customize a work item type which is different then customizing the card displayed on the Kanban board. You customize a WIT by adding fields, changing the workflow, adding custom rules and more. You can also add custom work item types and custom backlog levels. For details, see [Customize the On-premises XML process model](../../reference/on-premises-xml-process-model.md). 

::: moniker-end

You can either increase or simplify the information that displays on your cards. It all depends on what's of interest to your team. Does your team like to refer to work items by their ID? Do they want to see estimates? Do they want to highlight work items according to set criteria? Or, will just the bare bones of title and assignment suffice? 
Your best bet is to show fields on cards based on what your team frequently refers to or updates when using the Kanban and taskboards. Also, add fields with information that you can use to filter the board. If you're new to working with these tools, see [Kanban basics](../../boards/boards/kanban-basics.md) and [Sprint planning](../../boards/sprints/assign-work-sprint.md). 

[!INCLUDE [temp](../includes/prerequisites-team-settings.md)]


<a id="fields"></a>

## Update fields from the cards

Using the board views provides you with quick and easy ways to update work items as work progresses. Making daily or frequent updates helps everyone on your team stay in sync with what's been done and what needs doing next. 

To update status of a work item, you simply drag-and-drop cards to a different column. To change the order or stack ranking of a work item, you drag a card up or down within a column. 

For example, on the Kanban board, moving the card from Analyze to Develop updates the corresponding State field. In this case, the State field updates from Approved to Committed. 

![Kanban board, move a work item](media/ALM_CC_MoveCard.png)

Another handy feature is to simply update a field without having to open the work item. You can update most fields shown on the card. Here we reassign a requirement. 

![Kanban board, assign a work item](media/ALM_CC_UpdateFieldOnCard.png)

This quick update feature is particularly useful when you need to update a number of work items at once. For example, you can add estimates for backlog items on the Kanban board or update remaining work on the taskboard. 

To change the title, click the pencil icon in the upper-right corner. To add tags, double-click the work item to open it. And, just a reminder, you can't change the IDs for a work item, not from the card and not from within the form. 


<a id="styles" > </a>

## Highlight cards  

With styling rules, you can cause cards to change color when their corresponding work items meet criteria that you set. Here, we highlight severity 1 bugs by having the cards display as yellow. 

::: moniker range="tfs-2015"
This feature requires TFS 2015.1 or later versions.
::: moniker-end

::: moniker range=">= tfs-2018"
![Styling rule applied to bugs with Severity=1](media/customize-cards/card-style-s155-solo.png)
::: moniker-end
::: moniker range=">= tfs-2015 <= tfs-2017"
![Styling rule applied to bugs with Severity=1](media/kanban-board-card-style-rule-example.png)
::: moniker-end


### Example styling rules 

What rules should you apply to highlight work items? Here are a few examples and their associated criteria . 

> [!div class="mx-tdCol2BreakAll"]
> | Work items | Criteria |
> |------------|------------|
> | High priority items | `Priority = 1` |
> | High effort items | `Effort 20` or `Story Points 20` |
> | Stale items unchanged in the last 5 days | `Changed Date @Today-5` |
> |Title contains a key word | `Title Contains Yes` |
> |Severity 1 bugs | `Severity = 1 - Critical   AND   Work Item Type = Bug` |
> |High value business items | `Business Value 50` |
> |Items assigned to specific feature area  | `Area Path Under Fabrikam Fiber\Phone` |
> |Contains specific tag   | `Tags Contain RTM` |
> |Blocked tasks (Scrum process only) | `Blocked = Yes` |


<a id="kanban-board" > </a>


## Choose fields to appear on cards 

By showing a field on a card, you can edit that field directly on the board without having to open the card, unless it's a read-only field, such as the Change By and Changed Date fields. You can also customize the cards that appear on the Kanban board for features and epics. You follow similar steps, however you start from the [corresponding portfolio backlog](../../boards/backlogs/define-features-epics.md).  


::: moniker range=">= azure-devops-2019"
 
As a first step, you'll see that you can determine which fields appear on each card type. To add a custom field, you must first [add it to the process used to customize the project](../../organizations/settings/work//add-custom-field.md). 
::: moniker-end  

::: moniker range=">= tfs-2015 < azure-devops-2019"  
As a first step, you'll see that you can determine which fields appear on each card type. To add a custom field, you must first [add it to the WIT definition](../../reference/add-modify-field.md).  
::: moniker-end  


::: moniker range=">= azure-devops-2019"

1. [Open your Kanban board](kanban-quickstart.md). If you're not a team admin, [get added as one](../../organizations/settings/add-team-administrator.md). Only team and project admins can customize the Kanban board.

1. Choose the ![ ](../../media/icons/blue-gear.png) gear icon to configure the board and set general team settings.  

	> [!div class="mx-imgBorder"]
	> ![Open board settings for a team, vert nav](../../organizations/settings/media/configure-team/open-board-settings.png)  

2. Choose **Fields** and then a work item type to see all the settings you can modify. Your initial column settings will look something like this. 

	Here we choose User Story. Your choices will vary based on the [process](../../boards/work-items/guidance/choose-process.md) used to create your project and whether your team has chosen to [treat bugs like requirements or like tasks](../../organizations/settings/show-bugs-on-backlog.md).     

	> [!div class="mx-imgBorder"]
	> ![Settings,Fields, User Story tab (Agile process)](media/customize-cards/settings-fields-142.png) 

3. Place a check mark in the check box for those fields you want to have appear on the board. 

	If you want work estimates to show, check **Show Effort**. **Show Effort** corresponds to these fields: Effort ([Scrum](../../boards/work-items/guidance/scrum-process.md)), Story Points ([Agile](../../boards/work-items/guidance/agile-process.md)), and Size ([CMMI](../../boards/work-items/guidance/cmmi-process.md)).

4. To add a field, choose the ![ ](../media/icons/green_plus_icon.png) plus icon and enter the name of a field  you want to add. 

5. To remove a field, choose the ![ ](../../media/icons/delete-icon.png) delete icon next to the field.

6. When done with your changes, choose **Save**.

::: moniker-end  

::: moniker range=">= tfs-2017 <= tfs-2018"  
1. [Open your Kanban board](kanban-quickstart.md). If you're not a team admin, [get added as one](../../organizations/settings/add-team-administrator.md). Only team and project admins can customize the Kanban board.

1. Choose the ![ ](../../media/icons/team-settings-gear-icon.png) gear icon to open the common configuration settings dialog for the Kanban board. 

	![Kanban board, open common configuration settings](media/customize-cards/open-config-dialog.png) 

2. Choose **Fields** and then a work item type to see all the settings you can modify. Your initial column settings will look something like this. 

	Here we choose User Story. Your choices will vary based on the [process](../../boards/work-items/guidance/choose-process.md) used to create your project and whether your team has chosen to [treat bugs like requirements or like tasks](../../organizations/settings/show-bugs-on-backlog.md).     

	> [!div class="mx-imgBorder"]
	> ![Settings,Fields, User Story tab (Agile process)](media/customize-cards/settings-fields-142.png) 

3. Place a check mark in the check box for those fields you want to have appear on the board. 

	If you want work estimates to show, check **Show Effort**. **Show Effort** corresponds to these fields: Effort ([Scrum](../../boards/work-items/guidance/scrum-process.md)), Story Points ([Agile](../../boards/work-items/guidance/agile-process.md)), and Size ([CMMI](../../boards/work-items/guidance/cmmi-process.md)).

4. To add a field, choose the ![ ](../media/icons/green_plus_icon.png) plus icon and enter the name of a field  you want to add. 

5. To remove a field, choose the ![ ](../../media/icons/delete-icon.png) delete icon next to the field.

6. When done with your changes, choose **Save**.


::: moniker-end  

::: moniker range="tfs-2015"  

1. [Open your Kanban board](kanban-quickstart.md). If you're not a team admin, [get added as one](../../organizations/settings/add-team-administrator.md). Only team and project admins can customize the Kanban board.

1. Choose the ![ ](../../media/icons/team-settings-gear-icon.png) gear icon to open the common configuration settings dialog for the Kanban board. 

	![Kanban board, open common configuration settings](media/customize-cards/open-config-dialog.png) 

2. Choose **Fields** and then a work item type to see all the settings you can modify. Your initial column settings will look something like this. 

	Here we choose User Story. Your choices will vary based on the [process](../../boards/work-items/guidance/choose-process.md) used to create your project and whether your team has chosen to [treat bugs like requirements or like tasks](../../organizations/settings/show-bugs-on-backlog.md).     

	**TFS 2015.1 options:**      
	![TFS 2015.1 Kanban board, card customization dialog](media/vso-kanban-card-customize.png)  

	**TFS 2015 options:**      
	![Kanban board, card customization dialog](media/ALM_CC_KBCardOptions.png)  

3. Place a check mark in the check box for those fields you want to have appear on the board. 

	If you want work estimates to show, check **Show Effort** or **Show Cost**. These options will cause the following fields to appear based on the respective process: Effort ([Scrum](../../boards/work-items/guidance/scrum-process.md)), Story Points ([Agile](../../boards/work-items/guidance/agile-process.md)), and Size ([CMMI](../../boards/work-items/guidance/cmmi-process.md)).

4. To add a field, choose the ![ ](../../media/icons/add-icon.png) plus icon and enter the name of a field you want to add. 

5. To remove a field, choose the ![ ](../../media/icons/delete-icon.png) delete icon next to the field.

6. When done with your changes, choose **Save**.

::: moniker-end  



<a id="style-rule" > </a>  

## Define style rules to highlight cards  

You can apply style rules to change the color of cards on Kanban boards and taskboards.  

::: moniker range=">= azure-devops-2019"

1. [Open the Kanban board](kanban-quickstart.md) or [taskboard](../sprints/task-board.md) that you want to customize. If you're not a team admin, [get added as one](../../organizations/settings/add-team-administrator.md). Only team and project admins can customize boards.

2. Choose the ![ ](../../media/icons/blue-gear.png) gear icon to open the **Settings** dialog. 

3. Choose **Styles** to specify a style rule. Choose the ![ ](../../media/icons/green_plus_icon.png) plus icon to add a style. Select the color to apply to the card and define the criteria for the style rule. 

	In this example we show the **Styles** dialog for the taskboard. 

	> [!div class="mx-imgBorder"]  
	> ![Settings, Styles dialog](../sprints/media/customize/taskboard-styles-priority.png)

	Follow these rules when creating and ordering your style rules:
   - The criteria you specify works in a similar fashion as when [constructing a query](../../boards/queries/using-queries.md) 
   - All clauses are considered AND clauses, grouping clauses isn't supported  
   - Card rules apply to all work items that meet the rule criteria  
   - Rule color applies to work items based on the order in which rules are listed. If you add more than one style rule, make sure that you move them in the order of most importance. Simply drag them into the order you want them applied.  
   - You can quickly enable and disable a style rule     

     Here we add a Stale tasks rule which highlights tasks that haven't changed in the last five days.

     ![Taskboard, Style dialog, example style rule](../sprints/media/customize/task-board-card-style-rule-stale-tasks.png)   

4. To copy or delete a style rule, choose the ![ ](../../media/icons/actions-icon.png) actions icon and select **Clone** or **Delete**, respectively.

5. When done with your changes, choose **Save**.

::: moniker-end  

::: moniker range="tfs-2015"  
Requires TFS 2015.1 or later version.  
::: moniker-end  

::: moniker range=">= tfs-2015 <= tfs-2018"

1. [Open the Kanban board](kanban-quickstart.md) or [taskboard](../sprints/task-board.md) that you want to customize. If you're not a team admin, [get added as one](../../organizations/settings/add-team-administrator.md). Only team and project admins can customize boards.

2. Choose the ![ ](../../media/icons/team-settings-gear-icon.png) gear icon to open the **Settings** dialog. 

3. Choose **Styles** to specify a style rule. Choose the ![ ](../../media/icons/green_plus_icon.png) plus icon to add a style. Select the color to apply to the card and define the criteria for the style rule. 

	In this example we show the **Styles** dialog for the taskboard. 

	> [!div class="mx-imgBorder"]  
	> ![Settings, Styles dialog](../sprints/media/customize/taskboard-styles-priority.png)

	Follow these rules when creating and ordering your style rules:
   - The criteria you specify works in a similar fashion as when [constructing a query](../../boards/queries/using-queries.md) 
   - All clauses are considered AND clauses, grouping clauses isn't supported  
   - Card rules apply to all work items that meet the rule criteria  
   - Rule color applies to work items based on the order in which rules are listed. If you add more than one style rule, make sure that you move them in the order of most importance. Simply drag them into the order you want them applied.  
   - You can quickly enable and disable a style rule     

     Here we add a Stale tasks rule which highlights tasks that haven't changed in the last five days.

     ![taskboard, Style dialog, example style rule](../sprints/media/customize/task-board-card-style-rule-stale-tasks.png)   

4. To copy or delete a style rule, choose the ![ ](../../media/icons/actions-icon.png) actions icon and select **Clone** or **Delete**, respectively.

5. When done with your changes, choose **Save**.

::: moniker-end


<a id="color-tags" > </a>

## Color-code tags   

Prior to setting tag colors, first [add tags to backlog items](../../boards/queries/add-tags-to-work-items.md) that you want to highlight with color.  
 
::: moniker range="tfs-2015"  
Requires TFS 2015.1 or later version.  
::: moniker-end   

1. Open the Settings dialog for the Kanban board you want to customize. 

2. Choose **Tag colors** and then choose the ![ ](../../media/icons/green_plus_icon.png) plus icon to add a tag color. Then, select the tag and the color you want to appear on the cards.  

   ::: moniker range=">= tfs-2017"
   > [!div class="mx-imgBorder"]  
   > ![Settings, Tag colors dialog (Kanban)](media/customize-cards/settings-tag-colors.png) 
   ::: moniker-end   

   ::: moniker range="tfs-2015"  
   >  ![Settings, Tag colors dialog (Kanban), TFS 2015](media/kanban-card-customize-tag-colors.png)  
   ::: moniker-end   
   
   > [!TIP]
   > If tags don't display on the cards, choose **Fields** and make sure that you've checked **Show Tags**. 

3. When done with your changes, choose **Save**.

<a id="annotations" > </a>

::: moniker range=">= tfs-2017"  

## Enable annotations

With the Kanban board, you gain a rich set of tools and a rich set of customization options. Annotations provide visual cues about work items, indicating the number of tasks or tests that have been defined for that work item. Choose an annotation to expand the set or gain more information. 

As shown in the following examples, the **Task** and **Test** annotations indicate that two each of tasks and tests have been defined for the work item. If you find that there are some features you're not using, you can disable them from the **Annotations** tab. 

> [!div class="mx-tdBreakAll"]  
> | Task annotations  |Test annotations  |No annotations |
> |-------------|----------|----------|    
> |<img src="media/annotate-task.png" alt="Task annotations enabled" style="border: 1px solid #C3C3C3;" /> | <img src="media/annotate-test.png" alt="Test annotations enabled" style="border: 1px solid #C3C3C3;" />  | <img src="media/annotate-none.png" alt="Annotations disabled" style="border: 1px solid #C3C3C3;" /> | 

To learn more about using these features, see [Add task checklists](../../boards/boards/add-task-checklists.md) and [Add, run, and update inline tests](../../boards/boards/add-run-update-tests.md).  

::: moniker-end

::: moniker range="azure-devops-2019"

> [!NOTE]  
> If your project collection uses the On-premises XML process model to customize work tracking, you can enable work item types that you add to the Task Category to appear as a checklist on your product Kanban board. To learn how, see [Set up your backlogs and boards, Customize your Kanban Board checklist items](../backlogs/set-up-your-backlog.md#customize-checklist-2019). 

::: moniker-end



::: moniker range=">= tfs-2017"  

### Enable or disable an annotation

::: moniker-end

::: moniker range=">= azure-devops-2019"  

1. Open the Settings dialog for the Kanban board you want to customize. 
2. Choose **Annotations** and then check those annotations that you want enabled. For example, to enable tasks but disable tests, check the following boxes.     

	![Kanban board, Settings dialog, Annotations tab](media/customize-cards/annotate-settings-154.png)

	> [!NOTE]   
	> GitHub annotations requires Azure DevOps Server 2019 Update 1 or later version. To learn more about linking Azure Board work items to GitHub artifacts, see [Link GitHub commits, pull requests, and issues to work items](../github/link-to-from-github.md).

	When done with your changes, choose **Save**.

::: moniker-end

::: moniker range=">= tfs-2017 <= tfs-2018"  

1. Open the Settings dialog for the Kanban board you want to customize. 
2. Choose **Annotations** and then check those annotations that you want enabled. For example, to enable tasks but disable tests, check the following boxes.     

	![Kanban board, Settings dialog, Annotations tab](media/customize-cards/annotate-settings.png)

	When done with your changes, choose **Save**.

::: moniker-end

<a id="tests" > </a>

::: moniker range=">= tfs-2017"  

## Configure inline tests 

You can control the test plan under which inline tests you add through the Kanban board are created. You can choose to create a new test plan for each new test that you add, or add all new tests to a selected test plan going forward. 

::: moniker-end

::: moniker range=">= azure-devops-2019"

1. Open the Settings dialog for the Kanban board (product backlog only) you want to customize. 

2. Choose **Annotations** and make sure that **Test** annotation is enabled. This is a requirement to configure inline tests.

3. Choose **Tests**, and then choose the options you want. To select a test plan, choose the ![ ](../../media/icons/actions-icon.png) actions icon and select one test plan from the query provided.  

	> [!div class="mx-imgBorder"]  
	> ![Settings, Tag colors dialog (Kanban)](media/customize-cards/settings-tests.png)  

4. Save your changes. 

::: moniker-end

::: moniker range=">= tfs-2017 <= tfs-2018"

1. Open the Settings dialog for the Kanban board (product backlog only) you want to customize. 

2. Choose **Annotations** and make sure that **Test** annotation is enabled. This is a requirement to configure inline tests.

3. Choose **Tests**, and then choose the options you want. To select a test plan, choose the ![ ](../../media/icons/actions-icon.png) actions icon and select one test plan from the query provided.  

	![Settings dialog, Tests tab (Kanban), TFS 2015](media/c-cards-test-settings.png)   

4. Save your changes. 

::: moniker-end


::: moniker range=">= tfs-2017"

### Open the test plan, test suite from a card

From a card on the Kanban board, you can easily navigate to the underlying test plan and test suite under which the tests are created. Choose the ![ ](../../media/icons/open-icon.png) open icon to open another browser tab showing **Test** and associated test plan and test suite that controls the inline tests.

<img src="media/c-cards-navigate-to-test-suite.png" alt="Kanban board, Card, Go to test plan" style="border: 1px solid #C3C3C3;" />  

::: moniker-end

## Related articles

::: moniker range=">= azure-devops-2019"

- [Card reordering](reorder-cards.md)  
- [Manage and configure team tools](../../organizations/settings/manage-teams.md)
- [Setup your backlogs and boards](../backlogs/set-up-your-backlog.md)
- [Configure status badges](../github/configure-status-badges.md) 
- [Show bugs on backlogs and boards](../../organizations/settings/show-bugs-on-backlog.md)  
- [Select backlog navigation levels for your team](../../organizations/settings/select-backlog-navigation-levels.md)  
- [Set working days](../../organizations/settings/set-working-days.md) 

::: moniker-end

::: moniker range="<= tfs-2018"

- [Card reordering](reorder-cards.md)  
- [Manage and configure team tools](../../organizations/settings/manage-teams.md)
- [Setup your backlogs and boards](../backlogs/set-up-your-backlog.md)
- [Show bugs on backlogs and boards](../../organizations/settings/show-bugs-on-backlog.md)  
- [Select backlog navigation levels for your team](../../organizations/settings/select-backlog-navigation-levels.md)  
- [Set working days](../../organizations/settings/set-working-days.md) 


::: moniker-end