# 描述：RecyclerView嵌套在ScrollView中，RecyclerView高度不能正常显示问题？


*****************************************************
# 把RecyclerView用RelativeLayout包裹起来；
<!-- DEV NOTE: Outer wrapper relative layout is added intentionally to address issue that only happens on Marshmallow & Nougat devices (API 23 & 24).On marshmallow API 23, the "RecyclerView"`layout_height="wrap_content"` does NOT
occupy the height of all the elements added to it via adapter. The result is cut out items that is outside of device viewport when it loads initially.Wrapping "RecyclerView" with "RelativeLayout" fixes the issue on Marshmallow devices.
--> 
#
#
 <RelativeLayout
     android:layout_width="match_parent"
     android:layout_height="wrap_content"
     android:descendantFocusability="blocksDescendants">

        <android.support.v7.widget.RecyclerView
            android:id="@+id/my_recycler_view"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            tools:listitem="@layout/row_list_item">
 
        </android.support.v7.widget.RecyclerView>
 
 </RelativeLayout>


