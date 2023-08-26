To change the cell value while maintaining all cell properties in a DevExpress spreadsheet table, you can use the following steps:

1. Get the reference to the desired cell using the DevExpress API. You can use the cell's row and column indices or any other identifier that uniquely identifies the cell.

2. Retrieve the existing cell properties, such as formatting, style, or any other custom properties.

3. Modify the cell value as needed.

4. Apply the previously retrieved cell properties back to the cell.

Here's an example in C# using the DevExpress Spreadsheet API:

```csharp
// Assuming you have a reference to the DevExpress Spreadsheet control or worksheet object
Worksheet worksheet = spreadsheetControl1.ActiveWorksheet;

// Get the cell by row and column indices
Cell cell = worksheet.Cells[1, 1];

// Retrieve the existing cell properties
CellProperties properties = cell.GetProperties();

// Modify the cell value
cell.Value = "New Value";

// Apply the previously retrieved cell properties back to the cell
cell.SetProperties(properties);
```

This example demonstrates how to change the value of a cell while preserving all the cell properties. You can adapt this code to your specific programming language and environment.

Please note that the exact implementation may vary depending on the version of DevExpress and the programming language you are using. Make sure to refer to the DevExpress documentation or consult their support resources for more specific guidance.

Yes, you can set the values of a whole row in a DevExpress spreadsheet table in a single line using the `SetArray` method. Here's an example in C# using the DevExpress Spreadsheet API:

```csharp
// Assuming you have a reference to the DevExpress Spreadsheet control or worksheet object
Worksheet worksheet = spreadsheetControl1.ActiveWorksheet;

// Get the row index you want to modify
int rowIndex = 1;

// Create an array of values for the row
object[] values = new object[] { "Value 1", "Value 2", "Value 3", /* ... */ };

// Set the values of the row in a single line
worksheet.Rows[rowIndex].SetArray(values);
```

In this example, we create an array `values` that contains the desired values for each cell in the row. Then, we use the `SetArray` method of the `Row` object to set the values of the entire row in a single line.

Make sure to adjust the `rowIndex` variable to the desired row you want to modify, and populate the `values` array with the appropriate values for each cell in the row.

Please note that the `SetArray` method expects an array of objects, so you may need to convert or cast your values accordingly.

Remember to adapt this code to your specific programming language and environment, and consult the DevExpress documentation or support resources for more specific guidance.

Yes, you can combine the `SetArray` method with the approach of setting the values of a whole row while maintaining cell properties. Here's an example in C# using the DevExpress Spreadsheet API:

```csharp
// Assuming you have a reference to the DevExpress Spreadsheet control or worksheet object
Worksheet worksheet = spreadsheetControl1.ActiveWorksheet;

// Get the row index you want to modify
int rowIndex = 1;

// Create an array of values for the row
object[] values = new object[] { "Value 1", "Value 2", "Value 3", /* ... */ };

// Set the values of the row using SetArray
worksheet.Rows[rowIndex].SetArray(values);

// Iterate through each cell in the row
for (int columnIndex = 0; columnIndex < values.Length; columnIndex++)
{
    // Get the cell by row and column indices
    Cell cell = worksheet.Cells[rowIndex, columnIndex];

    // Retrieve the existing cell properties
    CellProperties properties = cell.GetProperties();

    // Apply the previously retrieved cell properties back to the cell
    cell.SetProperties(properties);
}
```

In this example, we first use the `SetArray` method to set the values of the cells in the row using the `values` array. Then, we iterate through each cell in the row and apply the cell properties individually.

By combining these two approaches, you can set the values of a whole row while maintaining the cell properties.

Remember to adapt this code to your specific programming language and environment, and consult the DevExpress documentation or support resources for more specific guidance.