This webscrapping exercise is based on the IBM Data Engineering Course


I'd be using websites that I visit often

First I need to import the libraries that are required


```python
!mamba install bs4==4.10.0 -y
!pip install lxml==4.6.4
!mamba install html5lib==1.1 -y
# !pip install requests==2.26.0
```

    'mamba' is not recognized as an internal or external command,
    operable program or batch file.
    

    Requirement already satisfied: lxml==4.6.4 in c:\users\patri\anaconda3\lib\site-packages (4.6.4)
    

    'mamba' is not recognized as an internal or external command,
    operable program or batch file.
    

Beautifulsoup Import!!


```python
from bs4 import BeautifulSoup # this module helps in web scrapping.
import requests  # this module helps us to download a web pagefrom 
```

Downloading from one of my most visited website


```python
url = "http://www.nairaland.com"
```


```python
data  = requests.get(url).text 
```

Creating a soup object using the Beautifulsoup constructor


```python
soup = BeautifulSoup(data,"html.parser") 
```

Time to scrap all links!!!


```python
for link in soup.find_all('a',href=True):  # in html anchor/link is represented by the tag <a>

    print(link.get('href'))

```

    https://www.nairaland.com/
    /register
    /login
    /trending
    /recent
    /topics
    /nairaland
    /politics
    /crime
    /romance
    /jobs
    /career
    /business
    /investment
    /nysc
    /education
    /autos
    /cartalk
    /properties
    /health
    /travel
    /family
    /culture
    /religion
    /food
    /diaries
    /ads
    /pets
    /agriculture
    /entertainment
    /jokes
    /tv-movies
    /music-radio
    /celebs
    /fashion
    /events
    /sports
    /gaming
    /forum-games
    /literature
    /science
    /programming
    /webmasters
    /computers
    /phones
    /graphics-video
    /techmarket
    /hopto/home/14942
    /hopto/home/111
    /hopto/home/111
    /news
    http://twitter.com/nairaland
    http://facebook.com/nigerianforum
    https://www.nairaland.com/1049481/how-place-targeted-ads-nairaland
    https://www.nairaland.com/6931614/nottingham-forest-knock-out-arsenal
    https://www.nairaland.com/6931545/zlatan-equals-ronaldos-record-scoring
    https://www.nairaland.com/6931736/governor-sanwo-olu-meets-nurses-resolves
    https://www.nairaland.com/6931612/osinbajo-mali-crisis-ecowas-not
    https://www.nairaland.com/6931623/osita-okechukwu-supporting-igbo-presidencyll
    https://www.nairaland.com/6931479/cbns-quarterly-forex-intervention-been
    https://www.nairaland.com/6931639/23-year-old-zimbabwean-prostitute-arrested-after
    https://www.nairaland.com/6931200/ethopia-vs-cape-verde-afcon/1#109226924
    https://www.nairaland.com/6931711/fire-guts-new-york-city
    https://www.nairaland.com/6931677/kano-govt-bans-shisha-smoking
    https://www.nairaland.com/6931665/army-refutes-reports-gun-battle
    https://www.nairaland.com/6931654/iswap-reshuffles-cabinet-after-super
    https://www.nairaland.com/6931416/bunch-plantain-spotted-juju-tied
    https://www.nairaland.com/6931385/papaya-ex-controversial-photoshoot-using
    https://www.nairaland.com/6930496/one-fact-every-wig-wearing
    https://www.nairaland.com/6888227/nottingham-forest-vs-arsenal-fa/2#109225439
    https://www.nairaland.com/6931264/strike-lagos-nurses-walk-out
    https://www.nairaland.com/6931255/zaidu-sanusi-keep-salah-quiet
    https://www.nairaland.com/6931120/sugar-daddy-tattoos-side-chics
    https://www.nairaland.com/6931514/terhemen-anongo-man-castrates-self
    https://www.nairaland.com/6929396/afcon-2021-cameroon-vs-burkina/3#109222221
    https://www.nairaland.com/6931483/afcon-2021-mendy-koulibaly-out
    https://www.nairaland.com/6931488/scenes-afcon-2021-opening-ceremony
    https://www.nairaland.com/6931102/young-girl-killed-stray-bullet
    https://www.nairaland.com/6931420/meet-youngest-players-afcon-2021
    https://www.nairaland.com/6931015/new-anambra-airport-records-142
    https://www.nairaland.com/6931410/buhari-signs-bills-establishing-adeyemi
    https://www.nairaland.com/6930306/soldiers-beat-policeman-duty-ibadan
    https://www.nairaland.com/6930966/national-assembly-leadership-behind-2022
    https://www.nairaland.com/6931409/mummy-g.o-visit-olufunmilayo-adebayos
    https://www.nairaland.com/6930931/gridlock-onitsha-people-travel-back
    https://www.nairaland.com/6931167/liverpool-vs-shrewsbury-town-fa/2#109220673
    https://www.nairaland.com/6930922/alexx-ekubo-before-giving-girls
    https://www.nairaland.com/6930692/bobrisky-sent-out-benin-asking
    https://www.nairaland.com/6930592/davido-looking-fly-friends-wedding
    https://www.nairaland.com/6930581/woman-forced-offload-goods-underpants
    https://www.nairaland.com/6930576/rock-collapse-tourists-during-boat
    https://www.nairaland.com/6931293/commercial-driver-stabs-lovers-husband
    https://www.nairaland.com/6931317/pictures-girls-supplied-bandits-sex
    https://www.nairaland.com/6930591/almost-bitten-puff-adder-corn
    https://www.nairaland.com/6930911/adetutu-ran-out-marriage-after
    https://www.nairaland.com/6930938/addicted-pornography-promiscuity-banky-w
    https://www.nairaland.com/6931050/ladies-fine-man-without-muscles
    https://www.nairaland.com/6930735/bbc-interview-olufunmilayo-adebayo-mummy
    https://www.nairaland.com/6931240/president-buhari-visit-ogun-state
    https://www.nairaland.com/6931152/sanusi-lamido-visits-kogi-world
    https://www.nairaland.com/6930904/serap-sues-lawan-gbajabiamila-over
    https://www.nairaland.com/6930817/police-arrests-maryam-abubakar-supplying
    https://www.nairaland.com/6930841/kori-bustard-collides-airlink-aircraft
    https://www.nairaland.com/6930795/2023-senators-scheming-governorship-seats
    https://www.nairaland.com/6930765/2023-jonathan-yet-get-backing
    https://www.nairaland.com/6930787/akeredolu-urges-chicken-consumption-southwest
    https://www.nairaland.com/6931043/ndlea-arrests-fake-security-agent
    https://www.nairaland.com/6930871/timothy-adegoke-oriyomi-hamzat-should
    https://www.nairaland.com/6930729/mohammed-zarma-rtd-deputy-comptroller
    https://www.nairaland.com/6931048/obituary-woman-beaten-death-husband
    https://www.nairaland.com/6930935/victor-osimhen-recovers-covid-19
    https://www.nairaland.com/6930870/30-abducted-students-one-teacher
    https://www.nairaland.com/6930622/covid-19-update-january-8-2021
    https://www.nairaland.com/6930736/stop-these-sexual-acts-2022
    https://www.nairaland.com/6927974/it-sin-married-people-watch
    https://www.nairaland.com/6930638/what-think-born-again-brothers
    https://www.nairaland.com/6930832/going-church-online-broadcast-service
    https://www.nairaland.com/6930663/why-must-baptised-name-jesus
    https://www.nairaland.com/6930325/goodluck-jonathan-coming-back-2023
    /news/1
    /news/2
    /news/3
    /news/4
    /news/5
    /news/6
    /news/7
    /news/8
    /news/9
    /news/10
    /hopto/home/111
    /hopto/home/11744
    /hopto/home/14928
    #up
    /
    http://www.seunosewa.com
    https://www.nairaland.com/1049481/how-place-targeted-ads-nairaland
    

Let's scrape the image tags


```python
for link in soup.find_all('img'):# in html image is represented by the tag <img>
    print(link)
    print(link.get('src'))
```

    <img src="/images/project/socseti.png"/>
    /images/project/socseti.png
    <img src="/images/project/socseti_hover.png"/>
    /images/project/socseti_hover.png
    <img src="/images/project/ttg.png" title="Main"/>
    /images/project/ttg.png
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img class="country_flag bordered" rel="flag" src="/images/flags/ng.gif" title="Nigeria"/>
    /images/flags/ng.gif
    <img alt="HotLog" border="0" src="https://hit2.hotlog.ru/cgi-bin/hotlog/count?s=2548708&amp;im=353"/>
    https://hit2.hotlog.ru/cgi-bin/hotlog/count?s=2548708&im=353
    

Scrapping Data from HTML Tables


```python
url="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DA0321EN-SkillsNetwork/labs/datasets/HTMLColorCodes.html"
```


```python
# get the contents of the webpage in text format and store in a variable called olajuwondata
olajuwondata  = requests.get(url).text
```


```python
soup = BeautifulSoup(olajuwondata,"html.parser")
```


```python
#find a html table in the web page
table = soup.find('table') # in html table is represented by the tag <table>
```


```python
#Get all rows from the table
for row in table.find_all('tr'): # in html table row is represented by the tag <tr>
    # Get all columns in each row.
    cols = row.find_all('td') # in html a column is represented by the tag <td>
    color_name = cols[2].string # store the value in column 3 as color_name
    color_code = cols[3].string # store the value in column 4 as color_code
    print("{}--->{}".format(color_name,color_code))
```

    Color Name--->None
    lightsalmon--->#FFA07A
    salmon--->#FA8072
    darksalmon--->#E9967A
    lightcoral--->#F08080
    coral--->#FF7F50
    tomato--->#FF6347
    orangered--->#FF4500
    gold--->#FFD700
    orange--->#FFA500
    darkorange--->#FF8C00
    lightyellow--->#FFFFE0
    lemonchiffon--->#FFFACD
    papayawhip--->#FFEFD5
    moccasin--->#FFE4B5
    peachpuff--->#FFDAB9
    palegoldenrod--->#EEE8AA
    khaki--->#F0E68C
    darkkhaki--->#BDB76B
    yellow--->#FFFF00
    lawngreen--->#7CFC00
    chartreuse--->#7FFF00
    limegreen--->#32CD32
    lime--->#00FF00
    forestgreen--->#228B22
    green--->#008000
    powderblue--->#B0E0E6
    lightblue--->#ADD8E6
    lightskyblue--->#87CEFA
    skyblue--->#87CEEB
    deepskyblue--->#00BFFF
    lightsteelblue--->#B0C4DE
    dodgerblue--->#1E90FF
    

Scrape data from HTML tables into a DataFrame using BeautifulSoup and Pandas


```python
import pandas as pd
```


```python
#I chose a website that has data about gas emissions
url = "https://en.wikipedia.org/wiki/World_population"
```


```python
# get the contents of the webpage in text format and store in a variable called data
data  = requests.get(url).text
```


```python
soup = BeautifulSoup(data,"html.parser")
```


```python
#find all html tables in the web page
tables = soup.find_all('table') # in html table is represented by the tag <table>
```


```python
for index,table in enumerate(tables):
    if ("10 most densely populated countries" in str(table)):
        table_index = index
print(table_index)
```

    5
    


```python
population_data = pd.DataFrame(columns=["Rank", "Country", "Population", "Area", "Density"])

for row in tables[table_index].tbody.find_all("tr"):
    col = row.find_all("td")
    if (col != []):
        rank = col[0].text
        country = col[1].text
        population = col[2].text.strip()
        area = col[3].text.strip()
        density = col[4].text.strip()
        population_data = population_data.append({"Rank":rank, "Country":country, "Population":population, "Area":area, "Density":density}, ignore_index=True)

population_data
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Country</th>
      <th>Population</th>
      <th>Area</th>
      <th>Density</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Singapore</td>
      <td>5,704,000</td>
      <td>710</td>
      <td>8,033</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Bangladesh</td>
      <td>172,020,000</td>
      <td>143,998</td>
      <td>1,195</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>\n Palestine\n\n</td>
      <td>5,266,785</td>
      <td>6,020</td>
      <td>847</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Lebanon</td>
      <td>6,856,000</td>
      <td>10,452</td>
      <td>656</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Taiwan</td>
      <td>23,604,000</td>
      <td>36,193</td>
      <td>652</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>South Korea</td>
      <td>51,781,000</td>
      <td>99,538</td>
      <td>520</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>Rwanda</td>
      <td>12,374,000</td>
      <td>26,338</td>
      <td>470</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>Haiti</td>
      <td>11,578,000</td>
      <td>27,065</td>
      <td>428</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>Netherlands</td>
      <td>17,680,000</td>
      <td>41,526</td>
      <td>426</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>Israel</td>
      <td>9,460,000</td>
      <td>22,072</td>
      <td>428</td>
    </tr>
  </tbody>
</table>
</div>



Scrape data from HTML tables into a DataFrame using read_html


```python
dataframe_list = pd.read_html(url, flavor='bs4')
```


```python
len(dataframe_list)
```




    26




```python
dataframe_list[5]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Country</th>
      <th>Population</th>
      <th>Area(km2)</th>
      <th>Density(pop/km2)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Singapore</td>
      <td>5704000</td>
      <td>710</td>
      <td>8033</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Bangladesh</td>
      <td>172020000</td>
      <td>143998</td>
      <td>1195</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Palestine</td>
      <td>5266785</td>
      <td>6020</td>
      <td>847</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Lebanon</td>
      <td>6856000</td>
      <td>10452</td>
      <td>656</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Taiwan</td>
      <td>23604000</td>
      <td>36193</td>
      <td>652</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>South Korea</td>
      <td>51781000</td>
      <td>99538</td>
      <td>520</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>Rwanda</td>
      <td>12374000</td>
      <td>26338</td>
      <td>470</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>Haiti</td>
      <td>11578000</td>
      <td>27065</td>
      <td>428</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>Netherlands</td>
      <td>17680000</td>
      <td>41526</td>
      <td>426</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>Israel</td>
      <td>9460000</td>
      <td>22072</td>
      <td>428</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.read_html(url, match="Countries ranking highly in both total population", flavor='bs4')[0]  #I decided to change the parameter around to find another table
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Country</th>
      <th>Population</th>
      <th>Area(km2)</th>
      <th>Density(pop/km2)</th>
      <th>Population trend</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>India</td>
      <td>1386620000</td>
      <td>3287240</td>
      <td>422</td>
      <td>Growing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Pakistan</td>
      <td>226280000</td>
      <td>803940</td>
      <td>281</td>
      <td>Rapidly growing</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Bangladesh</td>
      <td>172020000</td>
      <td>143998</td>
      <td>1195</td>
      <td>Rapidly growing</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Japan</td>
      <td>126010000</td>
      <td>377873</td>
      <td>333</td>
      <td>Declining[99]</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Philippines</td>
      <td>111340000</td>
      <td>300000</td>
      <td>371</td>
      <td>Growing</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>Vietnam</td>
      <td>96209000</td>
      <td>331689</td>
      <td>290</td>
      <td>Growing</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>United Kingdom</td>
      <td>66436000</td>
      <td>243610</td>
      <td>273</td>
      <td>Growing</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>South Korea</td>
      <td>51781000</td>
      <td>99538</td>
      <td>520</td>
      <td>Steady</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>Taiwan</td>
      <td>23604000</td>
      <td>36193</td>
      <td>652</td>
      <td>Steady</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>Sri Lanka</td>
      <td>21803000</td>
      <td>65610</td>
      <td>332</td>
      <td>Growing</td>
    </tr>
  </tbody>
</table>
</div>


