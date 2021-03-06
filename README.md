## Simple Tree Selector

node
- id # for checkbox label element
- title # view label
- value # return values
- children # nodes

## Dependencies

- jQuery 1.7+
- fontawesome 4.7

U can check `index.html`

#### Example

[https://shatle.github.io/jquery.treeSelector/](https://shatle.github.io/jquery.treeSelector/)

```
var rootNode = [{
  "id": "1",
  "title": "Node 0",
  "value": 1,
  "children": [
    {
      "id": "11",
      "title": "Node 11",
      "value": 11,
      "children": [
        {
          "id": "111",
          "title": "Node 111",
          "value": 111,
          "children": []
        },
        {
          "id": "112",
          "title": "Node 112",
          "value": 112,
          "children": []
        }
      ]
    },
    {
      "id": "12",
      "title": "Node 12",
      "value": 12,
      "children": [],
      "disabled":true
    },
    {
      "id": "13",
      "title": "Node 13",
      "value": 13,
      "children": []
    }
  ]
}]

$('div.treeSelector').treeSelector(rootNode, [11, 12], function (e, values) {
  console.info('onChange', e, values);
}, { 
  checkWithParent: true, 
  titleWithParent: true,
  notViewClickParentTitle: true
})
```

three options: 

```
 // options
var options = $.extend({
  // children checked/unchecked if true
  checkWithParent: false,
  // title with 'title1 - title 2' if true
  titleWithParent: false,
  // when item click, only view leaf title if true
  notViewClickParentTitle: false,
  // disabled a node
  disabled: function(node){
    return true/false
  },
  //
  emptyOptonPlaceholder: 'no options',
  // only get leafs value
  onlyLeaf: false,
  // custom node's props
  props: {
    label: 'title',
    value: 'value'
  },
  // every level indent
  indent: 10
}, params)

```
