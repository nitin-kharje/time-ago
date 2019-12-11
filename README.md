<?php
date_default_timezone_set('Asia/Calcutta');  //set time zone
// $t=time();
// echo date('Y-m-d');
echo  time_ago(date('2019-12-11 17:18:00'));//change the date and time to check the  variousoutput
<?php

function time_ago($timestamp){
	$time_ago = strtotime($timestamp);   //calculate timestamp in second since 1 jan 1970
	$current_time = time();			//show current system generated time.time 
	$time_difference = $current_time - $time_ago;
	$seconds = $time_difference;			//time in no of seconds
	$minutes = round($time_difference / 60);	   //value in 60 sec
	$hours = round($time_difference /3600);   	//time in 1hour =60sec *60sec
	$days = round($time_difference / 24 * 60 * 60);	//per day
	$weeks = round($time_difference / 7 * 24 * 60 * 60); 	//per weeks
	$months =round($seconds  /262944);			//per months
	$years =round($seconds/31553280);			//per years

	if($seconds<=60){

		return "just now";
	}
	else if($minutes<=60){
			 if($minutes==1){
			     return "1 minute ago";
		     }
			else{

			return "$minutes minute ago";
			}
		 }
		else if($hours<=24){
			     if($hours==1){

				   return"1 hour ago";
	  		      }
	   		    else{

	   			      return"$hours hour ago";
	  	 	     }
			 }
			 else if($days<=7){
				 	if($days==1){
				 		return"1 day ago";
				 	}
				 	else{
				 		return"$days day ago";
				 	}
			       }
			      else if($weeks<=5.3){  // 52/12 52 week in 1 year i.e. 12 months
			      			if($weeks<=1){
			      				return"1 week ago";
			      			}
			      			else{
			      				return"$weeks week ago";
			      			}
				         }
				         elseif($months<=12){
					         	if($months<1){
					         	return"1 month ago";
					        	 }
					       		 else{
					         	return"$months month ago";
					           }
					    	  }
				            else if($years<=1){
				         	    if($years==1){
				         		   return"1 year ago";
				         	    }
				         	    else{
				         		return"$years year ago";
				         	    }
				              }

 }


?>
