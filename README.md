# php-merge-array-key-with-same-value-and-sum-qty
Multiple Dimensional array and sum qty values which have the same two keys

```<?php

$array = array( 
			array(	
				"voucher_slug" => "nikhil-test",
            	"denomination" => 50,
            	"qty" => 10
        	),
        	array(	
				"voucher_slug" => "nikhil-test",
            	"denomination" => 50,
            	"qty" => 20
        	),
        	array(	
				"voucher_slug" => "nikhil-test1",
            	"denomination" => 100,
            	"qty" => 30
        	),
        	array(	
				"voucher_slug" => "nikhil-test",
            	"denomination" => 20,
            	"qty" => 40
        	),
        	array(	
				"voucher_slug" => "nikhil-test1",
            	"denomination" => 100,
            	"qty" => 50
        	),
        );

echo "<pre>";
	print_r($array);
echo "<pre/>";
$array2 = [];


foreach($array as $value) 
{
    if( isset( $array2[ $value['voucher_slug'].'_'.$value['denomination'] ] ) ) 
    {
        $temp = $array2[$value['voucher_slug'].'_'.$value['denomination']];

        $temp['denomination'] = $value['denomination'];
        $temp['qty'] += $value['qty'];


        $array2[ $value['voucher_slug'].'_'.$value['denomination'] ] = $temp;
    } 
    else 
    {
        $array2[ $value['voucher_slug'].'_'.$value['denomination'] ] = $value;
    }
}

echo "<pre>";
	print_r($array2);
echo "<pre/>";

```
