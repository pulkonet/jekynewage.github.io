---
layout: post
title: Adapters
tagline: Using lists in android
visible: 1
category: Adapters
tags: [Android Adapter]
---

## Adapters in Android 

An Adapter object acts as a bridge between an AdapterView and the underlying data for that view. The Adapter provides access to the data items. The Adapter is also responsible for making a View for each item in the data set.

Regarding the challenge, we have to display the list of criminals. This can be done using ListView and ListFragment. We need an adapter to bind the data fetched from the database to corresponding row in the list. On clicking rows of listview, we need to show the  details of the corresponding criminal. This can be done by adding `setOnClickListner()` to row item in the list. 

## ListFragment ##

[Fragment](http://developer.android.com/guide/components/fragments.html) is a piece of activity's UI. We prefer to create the user interface using fragments and add these fragments to activity so that they can be reused. It's lifecycle is similar to that of the activity.


[ListFragment](http://developer.android.com/reference/android/app/ListFragment.html) displays a list of items by binding to a data source such as an array or Cursor, and exposes event handlers when the user selects an item.

It hosts a ListView object that can be bound to different data sources, typically either an array or a Cursor holding query results. 

### How do we add Fragment to Activity?
	
The following snippet illustrates how do we add the fragment to activity. This should be done in the `onCreate`  method of activity.

	fManager = getSupportFragmentManager();
	fTranslation = fManager.beginTransaction();
	exampleListFragment = new ExampleListFragment(); 	
	fTranslation.replace(R.id.list_fragment,exampleListFragment);
	fTranslation.commit();

The exampleListFragment is declared as :

    public class ExampleListFragment extends ListFragment{

	ListView listview;
	List<RowItem> rowlist;
        
	@Override
	public View onCreateView(LayoutInflater inflater, ViewGroup container,Bundle savedInstanceState) {
	
	View v = inflater.inflate(R.layout.list_fragment,
				container, false);
	listview = (ListView)v.findViewById(android.R.id.list);
	
	//data to be binded with list
    rowlist = new ArrayList<RowItem>(); 
    
    rowlist.add (new RowItem(.....));
    ...
    ... //adding items to rowlist
    
	//adding adapter to listview    
	list.setAdapter(new RowListAdapter(context, result));

		//returns ListFragment ViewGroup  
		return v;
	 }
	
    }	

 [ListView](http://developer.android.com/reference/android/widget/ListView.html) is a `ViewGroup` which shows list of scrollable items. ([ViewGroup](http://developer.android.com/reference/android/view/ViewGroup.html) is a special view that can contain other views. The `ViewGroup` is the base class for layouts and views containers.)
      
      
[Here](https://www.airpair.com/android/list-fragment-android-studio) is quick tutorial on `ListFragment` using AndroidStudio.


----------


## Adapter ##

[Adapter](http://developer.android.com/reference/android/widget/Adapter.html) in android acts as bridge  between an `AdapterView` and the underlying data for that view.  The Adapter provides access to the data items. The Adapter is also responsible for making a View for each item in the data set. 


![enter image description here](http://www.edureka.co/blog/wp-content/uploads/2013/03/adapters-1.png)

Data can be information obtained from database or server  or it can be already present in program. There are many subclasses of Adapter, for example [CursorAdapter](http://developer.android.com/reference/android/widget/CursorAdapter.html), [ArrayAdapter](http://developer.android.com/reference/android/widget/ArrayAdapter.html) etc.


## BaseAdapter ##
[BaseAdapter](http://developer.android.com/reference/android/widget/BaseAdapter.html) is an abstract class which implements ListAdapter and SpinnerAdapter Interface. Hence, we may use it for implementing both [ListView](http://developer.android.com/reference/android/widget/ListView.html) and [Spinner](http://developer.android.com/guide/topics/ui/controls/spinner.html). Following methods are necessary to implement for creating a subclass of BaseAdapter:

 - `getCount()` : `int` returns number of rows in list
 - `getItem(int position)`: `Object` returns Item object 
 - `getItemId(int position)`: `long` returns the id of the item at position `position`
 - `getView(int arg0, View arg1, ViewGroup arg2)`: `View`

  
### How getView() works?

Adapters call the `getView()` method which returns a view for each item within the adapter view. The layout format and the corresponding data for an item within the adapter view is set in the `getView()` method. Due to performance reasons, `getView()` doesn't returns a new View object every time it is called. So what Android does is that it recycles the views and reuses the view that goes out of focus.

![Visual representation of this recycle process:](http://www.edureka.co/blog/wp-content/uploads/2013/03/021-1.png)



## CursorAdapter ##

[Cursor](http://developer.android.com/reference/android/database/Cursor.html) is an interface which provides random read-write access to result set returned by read write query. This interface has been explained in our previous post on [databases in android](https://mobile.sdslabs.co/2015/01/08/databases-in-android/).

  [CursorAdapter](http://developer.android.com/reference/android/widget/CursorAdapter.html) is a subclass of BaseAdapter. It is used to bind cursor data qureied from database to AdapterView. Cursor adapter has following abstract methods,
    
 - `newView(Context context, Cursor cursor, ViewGroup parent)`: `View` 
 This method creates new AdapterView to hold data.
 
 - `bindView(View view, Context context, Cursor cursor)`: `void` 
 In this method CursorAdapter just elements to list's view.

[SimpleCursorAdapter](http://developer.android.com/reference/android/widget/SimpleCursorAdapter.html) is subclass of CursorAdapter. If we use it, we don't have to create separate Adapter's subclass. Here is a sample code that shows how do we attach this to listview.

        // The desired columns to be bound    
        String[] columns = new String[] { People.NAME, People.NUMBER };
    
        // XML defined views which the data will be bound to
        int[] to = new int[] { R.id.name_entry, R.id.number_entry };
 
        // Create the adapter using the cursor pointing to the desired data as well as the layout information
        SimpleCursorAdapter mAdapter = new SimpleCursorAdapter(this, R.layout.list_example_entry, cursor, columns, to);
    
        // Set this adapter as your list's adapter
        this.setListAdapter(mAdapter);
    

Array Adapter
-------------
[Array Adapter](http://developer.android.com/reference/android/widget/ArrayAdapter.html) is subclass of BaseAdapter. It is used to bind data in arrayList to AdapterView. 

In this type of adapter, we pass List, context of activity and layout of entry as attribute, but layout of entry can be only those which are already present in the library. We associate an adapter with View.

 ---------

Custom Adapters for ListView
--------------

[Custom Adapter](http://stackoverflow.com/questions/8166497/custom-adapter-for-list-view) is used when we want to design and add more UI components  to an item of ListView or GridView. We build this class on our own. This class extends Adapter or Adapter's subclass.   In the getView() method of class, we may set custom content View. 



 <center> <img src="http://i-cdn.phonearena.com/images/articles/126045-image/Androids-new-clothes.jpg" height="500" /> </center>
 *Image:  ListView using CustomAdapter*


In general, CustomArrayAdapter overrides the following methods of ArrayAdapter,

Example code: getView() 

        public View getView(int position, View convertView, ViewGroup parent)
        {
            View entryView = convertView;
            if(convertView == null){
                LayoutInflater layoutInflater = (LayoutInflater)context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
                entryView = layoutInflater.inflate(R.layout.entry_item, parent,false);
            }
    	
            TextView entryUser =(TextView)entryView.findViewById(R.id.entry_user);
            //and so on, add all UI components 
            //setOnClickListener events to button components

            return entryView;
        }


Similarly, we can create CustomCursorAdapter by extending CursorAdapter. SubClass of CursorAdapter must have to override the following methods of CursorAdapter. Here is sample code for `newView()` and `bindView()` abstract methods of CursorAdapter.
 

         /**
         *Makes a new view to hold the data pointed to by cursor.
         */
        @Override
        public View newView(Context context, Cursor cursor, ViewGroup parent)
        {
            LayoutInflater inflater = LayoutInflater.from(context);
            View newView = inflater.inflate(
                    android.R.layout.simple_list_item_1, parent, false);
            return newView;
        } 

        @Override
        public void bindView(View view, Context context, Cursor cursor)
        {
            TextView txtView = (TextView)view.findViewById(android.R.id.text1);
            txtView.setText(cursor.getString(
            cursor.getColumnIndex("person")));
        }


 [Here](http://thinkandroid.wordpress.com/2010/01/11/custom-cursoradapters/) is a quick tutorial on CustomCursorAdapter.

This concludes the post on adapters. Hope you will now be able to implement lists in your app. 

Keep watching for our next post on google maps. Till then goodbye and happy coding !
