# gz_lianjia

Learn to use _Requests_ and _BeautifulSoup_, to get Guangzhou renting houses and xiaoqu information from [https://gz.lianjia.com/](https://gz.lianjia.com/), and save the information to csv file.

### Usage

```bash
python gz_lianjia.py {district} {type} [-x val] {output_csv}

# Get 3 bedrooms houses in Tianhe district, area is from 120 to 144 squaremeters, save to zufang_dest.csv.
python gz_lianjia.py tianhe zufang -a 130 -b 3 zufang_dest.csv
options:
-a --areaaround: range {39,50,70,90,110,130}  
-b --bedrooms: range {1,2,3,4,5,6}
# Get xiaoqu in haizhu district which were established within 20 year (1998~2018), save to xiaoqu_dest.csv.
python gz_lianjia.py haizhu xiaoqu -y 20 xiaoqu_dest.csv
options:
-y --yearswithin: range {5, 10, 15, 20, 21}
```

### History

##### Jan 31, 2018
Use argparse to parse the command line inputs, no more source code change needed in order to get different types of information.  

Take searching criteria and other settings out and put them into another file, create a new repo for it.

##### Jan 29, 2018
Add feature to get xiaoqu list from a district, hence make_url function is also modified.  

> To get 3-bedroom houses in Tianhe district:  
  ```collect_houses('tianhe', '3', 'tianhe_3_bedrooms.csv')```  
  To get Xiaoqu list that established within 10 years in Tianhe district:  
  ```collect_xiaoqu('tianhe', 'tianhe_xiaoqu_2008.csv', '<10')```  

  Still rough too, considering using args parser.

##### Jan 18, 2018
It's a really rough version, only basic function is implemented. To get different results by district or bedroom number, source code should be modified.  
>To get 3-bedroom houses in Tianhe district:  
```process('tianhe', '3', 'gz.csv')```
