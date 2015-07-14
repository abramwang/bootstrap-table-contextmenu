Bootstrap table context menu
=======================

This is a light-weight extension for [Bootstrap table](http://wenzhixin.net.cn/p/bootstrap-table/docs/extensions.html) that adds context menu support.

Usage
-----
### Simple example
First of all, you need to include Bootstrap and this extension:
```
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">

    <script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>
    <script src="../src/bootstrap-table-contextmenu.js"></script>
```

Then you can create placeholder element and initialize it with javascript as a filter:
```
<body>
    <div class="container">
      <div class="row">
        <table id='grid'>
            <thead>
              <tr>
                <th data-field='itemid'>Item ID</th>
                <th data-field='name'>Name</th>
                <th data-field='price'>Price</th>
              </tr>
            </thead>
            <tbody>
              <tr><td>1</td><td>ABC</td><td>$1.00</td></tr>
              <tr><td>2</td><td>DEF</td><td>$2.00</td></tr>
              <tr><td>3</td><td>GHI</td><td>$3.00</td></tr>
              <tr><td>4</td><td>XYZ</td><td>$4.00</td></tr>
            </tbody>
        </table>
      </div>  
    </div>
  
    <!-- context menu -->
    <ul id="context-menu" class="dropdown-menu">
        <li data-item="edit">Edit</li>
        <li data-item="delete">Delete</li>
        <li data-item="action1">Action Here</li>
        <li data-item="action2">And Action Here</li>
    </ul>  
</body>

<script>
  $grid.bootstrapTable({
      contextMenu: '#context-menu',
      onContextMenuItem: function(row, $el){
          if($el.data("item") == "edit"){
              alert(row.itemid);
          }
      }
  });
</script>
```
