📘 Power Automate Learning Summary – Inventory Management Workflow with SharePoint & Microsoft Forms
🗓 Date: 2025-05-21
🔧 Tools Used:
Microsoft Forms: For user input (Item ID, Item Name, Quantity)

SharePoint List: To store and manage inventory data

Power Automate: For automation flow

Compose Action: For data processing

✅ Objective:
To create an automated inventory management system where:

Data is submitted via Microsoft Forms

The form includes: Item ID, Item Name, and Quantity (as strings)

Power Automate checks if the item already exists in a SharePoint list

If it exists, it adds the new quantity to the existing one

If it doesn’t exist, it adds a new item to the SharePoint list

🔁 Workflow Steps:
1.Trigger: Form submitted via Microsoft Forms

2.Action: Use Get response details to extract submitted values

3.Action: Use Compose to convert quantity string to integer using:

int(triggerOutputs()?['body/Quantity'])

4.Action: Use Get items (SharePoint) to search for an existing item by ID

5.Condition: If item with the same ID exists
Calculate new total with Compose:
add(int(triggerOutputs()?['body/Quantity']), int(existingQuantity))

Use Update item to update the quantity

6.Else:

Use Create item to add a new row in SharePoint


💡 Key Learnings:
How to use Compose for converting and processing string data

Using coalesce() and toUpper() to handle nulls and format strings

Conditional logic to decide between updating or creating a SharePoint item

End-to-end automation between Microsoft Forms and SharePoint

📦 Potential Improvements:
Add error handling for invalid input formats

Log rejected submissions to a separate list

Include timestamp and user tracking