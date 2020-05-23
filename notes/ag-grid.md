# ag-grid for react

- check out [tachyons](https://medium.com/@simonswiss/full-re-write-in-10-days-with-tachyons-and-functional-css-a-case-study-part-4-b565745ca1e5)

-   select first row

```javascript
const rowNode = this.gridApi.getDisplayedRowAtIndex(0);
rowNode.setSelected(true);
```

-   select row by id

```javascript
const rowNode = getRowNode(id);
rowNode.setSelected(true);
```

-   [change detection](https://www.ag-grid.com/javascript-grid-change-detection/)

```javascript
<AgGridReact
    columnDefs={this.state.columnDefs}
    aggregateOnlyChangedColumns={true}
    aggFuncs={this.state.aggFuncs}
    columnTypes={this.state.columnTypes}
    autoGroupColumnDef={this.state.autoGroupColumnDef}
    groupDefaultExpanded={this.state.groupDefaultExpanded}
    rowData={this.state.rowData}
    suppressAggFuncInHeader={true}
    animateRows={true}
    enableSorting={true}
    enableColResize={true}
    getRowNodeId={this.getRowNodeId}
    onGridReady={this.onGridReady}
    onGridReady={this.onGridReady.bind(this)}
    onRowSelected={this.onRowSelected}
    // callback tells the grid to use the 'id' attribute for id's
    // id's should always be strings
    gridOptions.getRowNodeId = function(data) {
        return data.id;
    };
/>
```

```javascript
  onGridReady(params) {
    this.gridApi = params.api;
    this.gridColumnApi = params.columnApi;

    const httpRequest = new XMLHttpRequest();
    const updateData = data => {
      params.api.setRowData(data.slice(0, 100));
    };

    httpRequest.open(
      "GET",
      "https://raw.githubusercontent.com/ag-grid/ag-grid/master/packages/ag-grid-docs/src/olympicWinnersSmall.json"
    );
    httpRequest.send();
    httpRequest.onreadystatechange = () => {
      if (httpRequest.readyState === 4 && httpRequest.status === 200) {
        updateData(JSON.parse(httpRequest.responseText));
      }
    };
  }
```
