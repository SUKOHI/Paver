Paver
=====

A PHP package mainly developed for Laravel to generate PHP codes using column names of specified table.

Example
====
    $item->id = '';
    $item->title = '';
    $item->created_at = '';
    $item->updated_at = '';
 
Installation&setting for Laravel
====

After installation using composer, add the followings to the array in  app/config/app.php

    'providers' => array(  
        ...Others...,  
        'Sukohi\Paver\PaverServiceProvider', 
    )

Also

    'aliases' => array(  
        ...Others...,  
        'Paver' =>'Sukohi\Paver\Facades\Paver',
    )

Usage
====

**Basic setting**

    $paver = Paver::table('table_name');
    
    // Example
    $paver = Paver::table('items');

**Minimal way**

    echo $paver->format();
    
    // Example
    $item->id = '';
    $item->title = '';
    $item->created_at = '';
    $item->updated_at = '';

**with Argument(s)**  

    echo $paver->format('argument');
    
    // Example
    $item->id = $id;
    $item->title = $title;
    $item->created_at = $created_at;
    $item->updated_at = $updated_at;

**with Input::get('\*\*\*')**

    echo $paver->format('input');
    
    // Example
    $item->id = Input::get('id');
    $item->title = Input::get('title');
    $item->created_at = Input::get('created_at');
    $item->updated_at = Input::get('updated_at');

**with foreach()**
    
    echo $paver->format('foreach');
    
    // Example
    $id = $item->id;
    $title = $item->title;
    $created_at = $item->created_at;
    $updated_at = $item->updated_at;
    
**Json**

    echo $paver->format('json');
    
    // Example
    ["id","title","position","created_at","updated_at"]
    
**Array**
    
    echo $paver->format('array');
    
    // Example
    $columns = ['id', 'title', 'position', 'created_at', 'updated_at'];
    
**Custom format**

You can also use custom formats like this.

    echo $paver->format(':table and :column.');
    
    // Example
    item and id.
    item and title.
    item and created_at.
    item and updated_at.

* :table will be replaced with singular table name.  
* :column will be replaced with a column name of the specified table.

License
====
This package is licensed under the MIT License.

Copyright 2014 Sukohi Kuhoh