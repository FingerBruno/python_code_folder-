**how to set a columns as a index** 

    column_name = set here de column name 
    df = df.set_index(column_name)

**how to loop a dictionary** 
	https://realpython.com/iterate-through-dictionary-python/
	
    for key, value in a_dict.items():
	     print(key, '->', value)
  
    color -> blue
    fruit -> apple
    pet -> dog


**how to a drop a column**

    cols = "-1"
    df.drop(df.columns[-1],axis=1,inplace=True)

**how to convert a list into a list of tuples**
https://blog.finxter.com/how-to-convert-list-of-lists-to-list-of-tuples-in-python/#:~:text=If%20you're%20in%20a,with%20varying%20number%20of%20elements.

    lst = [[1, 2], [3, 4], [5, 6]]
    tuples = [tuple(x) for x in lst]
    print(tuples)


**how to scrape a table from dinamic page** 

    url = ''
    browser = start_chrome(url, headless=True)
    soup= BeautifulSoup(browser.page_source, 'html.parser')
    
    quotes = soup.find_all('div', {'class':'quote'})
**how to scrape next item from a tag** 

    table = soup.find('span', {'id':'Classificação'}).find_next("table")

**transform a scraped table into a pandas df** 

    table_rows = table.find_all('tr')
    res = []
    
    for tr in table_rows:
        td = tr.find_all('td')
        row = [tr.text.strip() for tr in td if tr.text.strip()]
        if row:
            res.append(row)
            
    df = pd.DataFrame(res, columns=[])
    print(df)

**export a df as a json** 
```
data = df.to_json('./youngest2wingp.json', orient='index')
}
```
```
bruno finger
```
