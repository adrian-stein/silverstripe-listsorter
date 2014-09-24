# SilverStripe List Sorter

A front-end control for sorting SilverStripe lists easily. The aim of this module is to make sorting lists as simple as it is to use PaginatedList.

## Requirements

 * SilverStripe 3+

## Usage

Make a public function on your controller:
```php
function getSorter(){
	$sorts = array(
		'Created' => 'Date',
		'Title',
		'Author'
	);
	return new ListSorter($this->request,$sorts);
}
```

Call that function when updating your list:
```php
public function getSortableChildren() {
	$list = $this->Children();
	$list = $this->getSorter()->sortList($list);
	return $list;
}

```

Use my template or roll your own.

```
<% include Sorter %>
<ul>
<% loop SortableChildren %>
	<li>$Title</li>
<% end_loop %>
</ul>
```

## Contributions

...are welcomed via pull request. Check the [issues list](https://github.com/burnbright/silverstripe-listsorter/issues) first.
