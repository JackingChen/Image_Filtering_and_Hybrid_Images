# JackChen <span style="color:red">(104061563)</span>

# Project 1 / Image Filtering and Hybrid Images

## Overview
The project is related to 
> hybrid image


## Implementation
1. zero padding (I use mirror padding method)
	* 	Example(I only domenstrate lefttop and left side): 
`
	%lefttop
		 for i=indexbase_c:-1:1
		     for j=indexbase_r:-1:1
        		   img_pad(j,i)=img_g(indexbase_r-j+1,indexbase_c-i+1);
	  	     end
		end
		%left
		 for i=indexbase_c:-1:1
		     for j=indexbase_r:rows
		           img_pad(j,i)=img_g(j-indexbase_r+1,indexbase_c-i+1);
		    end
	        end`
	result : 
	<img src="padded_example.bmp" width="24%"/>

2. convolution 
		`tmp_val=filter.*img_pad(start_r-floor(indexbase_r/2):start_r+floor(indexbase_r/2),start_c-floor(indexbase_c/):start_c+floor(indexbase_c/2));%multiply selected area on the image and the filter
            	value=sum(sum(tmp_val));
            	output_tmp(j,i)=value; 	`
	
   explanation: 
   I used matrix multiplication to multiply selected window of the original picture and the filter. Then I used sum() funciton to add the value up. At last, assign the value to a new matrix.

3. Repeat mirror padding and convolution for three dimentions 
   



## Installation
* Matlab https://ca.nctu.edu.tw/news-list/software-release/208-matlab-r2014b-release
* execute the proj1.m file in the code directory.

### Results

<table border=1>
<tr>
<td>
<img src="birdane.jpg" width="24%"/>
<img src="catdog.jpg"  width="24%"/>
<img src="einstlyn.jpg" width="24%"/>
<img src="fishmarin.jpg" width="24%"/>
<img src="result4.bmp" width="24%"/>
<img src="result5.bmp" width="24%"/>
<img src="result6.bmp" width="24%"/>
</td>
</tr>


</table>
