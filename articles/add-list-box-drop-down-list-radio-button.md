<properties
	pageTitle="Add a listbox, drop-down list, and radio button controls in PowerApps Studio | Microsoft Azure"
	description=""
	services=""
	documentationCenter=""
	authors="MandiOhlinger"
	manager="dwrede"
	editor=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na" 
   ms.date="10/28/2015"
   ms.author="mandia"/>


# Add a list box, drop-down list, or radio button control

PowerApps Studio includes multi-select and single-select options, including a listbox, drop-down list, and radio button controls. In this topic, we add these controls and use a Table to build the lists. When an item is selected in the list, it updates other controls.

### Prerequisites

- Install [PowerApps Studio](http://aka.ms/powerappsinstall). Create a new app or open an existing app in PowerApps. 
- To familiarize yourself with configuring controls in PowerApps, step through the [configure a control](get-started-test-drive.md#configure-a-control).


## Add a listbox

1. On the **Insert** tab, select **Controls**, and then select **ListBox**:  
![][2]  
2. Rename the listbox to **MyListBox**:  
![][3]  
3. Set its **Items** property to the following expression:  
```["circle","triangle","rectangle"]```  <br/>

	Your designer looks similar to the following:  
	![][4]  
4. On the **Insert** tab, select **Shapes**, select the **circle**, and move it under the listbox:  
![][5]  

5. Add a triangle and a rectangle, and then arrange the shapes in a row under the listbox:  
![][6]  

6. Set the **Visible** property of the following shapes to the following functions:  

	Shape | Set function to | Example
--- | --- | ---
circle | ```If("circle" in MyListbox!SelectedItems!Value, true)``` | ![][7]
triangle | ```If("triangle" in MyListbox!SelectedItems!Value, true)``` | ![][8]
rectangle | ```If("rectangle" in MyListbox!SelectedItems!Value, true)``` | ![][9]

7. Preview what you've created ![][1]. Select the different shapes in the listbox. Only the shape or shapes you select appear. Press ESC to go back to your screen.

In these steps, you used an expression to create a list of items in a listbox. Depending on what you choose in the list box, different shapes are displayed. You can apply this to other elements within your business. For example, you can use a listbox to display product images, product descriptions, and so on.


## Add a drop-down list and a radio button control

> [AZURE.NOTE] The following steps apply to radio button controls and drop-down lists. Both controls are created the same way.

1. On the **Home** tab, select **New Screen**.
2. On the **Insert** tab, select **Controls**, select **Radio**, and then rename the radio control to **Choices**:  
![][10]  

	![][11]  

3. Set the radio control **Items** property to the following function:  
```["red","green","blue"]```  <br/>

	![][12]  

	If needed, resize the control to show all the options.

4. On the Insert tab, select **Shapes**, and select the circle. Set the **Fill** property of the circle to the following function:  
```If(Choices!Selected!Value = "red", RGBA(192, 0, 0, 1), Choices!Selected!Value = "green", RGBA(0, 176, 80, 1), Choices!Selected!Value = "blue", RGBA(0, 32, 96, 1))```  

	![][13]  

	In this function, the circle changes its color depending on which radio button you choose.

5. Move the circle under the radio control. You setup should look similar to the following:  
![][14]  
6. Preview what you've created: ![][1]. Select the different radio buttons to change the color of the circle. Press ESC to go back to your screen.

Now, try the same steps using the drop-down control:  
	![][15]  

1. Add a new screen, add the drop-down control, and rename it to **DDChoices**. Add the circle and set its **Fill** property to the following function:  
```If(DDChoices!Selected!Value = "red", RGBA(192, 0, 0, 1), DDChoices!Selected!Value = "green", RGBA(0, 176, 80, 1), DDChoices!Selected!Value = "blue", RGBA(0, 32, 96, 1))```

2. Preview what you've created: ![][1]. Select the different options to change the color of the circle.

In these steps, you used an expression to create the items in a radio button and  a drop-down control. When you click an item within the control (radio or drop-down), the property of another control (the circle) changes.


## Tips and Tricks
- You can also use different data sources to populate the items within these controls. For example, you can use an Excel table as a data source. Then display the Excel data in a list box, and so on.
- At anytime, you can select the preview button (![][1]) to see what you created and test it.
- When designing your app, you can resize the controls and move them around using click-and-drag.
- Press **ESC** to close the preview window and go back to the designer.
- We renamed some controls, including the listbox. Renaming controls is optional. When using controls in expressions, it's easier to remember the control names if you rename them. 


## What you learned

In this topic, you:

- Added radio buttons and a listbox to the app.
- Using an expression, you populated the items within the lists.
- You used Excel-like functions to update properties on other controls. For example, if a list item or radio button is selected, a shape changes color or is displayed in the app.


[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[7]: ./media/add-list-box-drop-down-list-radio-button/visiblecircle.png
[8]: ./media/add-list-box-drop-down-list-radio-button/visibletriangle.png
[9]: ./media/add-list-box-drop-down-list-radio-button/visiblerectangle.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[11]: ./media/add-list-box-drop-down-list-radio-button/renameradio.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[13]: ./media/add-list-box-drop-down-list-radio-button/fillradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png