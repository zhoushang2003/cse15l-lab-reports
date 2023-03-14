# Find Command Options

`-name`

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -name HandRHawaii.txt
berlitz1/HandRHawaii.txt`

Using `-name` option to find the exact location of the specified file.

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -name HandRIbiza.txt
berlitz1/HandRIbiza.txt`

Using `-name` option to find the exact location of the specified file.

`-type`

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -type d               
berlitz1`

Using `-type d` option to find directories in working directory.

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz2 -type d               
berlitz2`

Using `-type d` option to find directories in working directory.

`-mtime`

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -mtime -1
berlitz1
berlitz1/HandRLasVegas.txt
berlitz1/HistoryJapan.txt
berlitz1/IntroMalaysia.txt
berlitz1/HandRIstanbul.txt
berlitz1/HistoryJamaica.txt
berlitz1/HandRJamaica.txt
berlitz1/HandRHongKong.txt
berlitz1/HistoryEgypt.txt`

Using `-mtime` option to see whether the file is modified during the given time. Here -1 stands for yesterday.

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -mtime 1
 `

Using `-mtime` option to see whether the file is modified during the given time. Here 1 stands for today.

`-size`

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -size +10M
`

Using `-size` option to see if there exist file that is larger than the size given. Here we have no file that is larger than 10 mb.

`(base) zhoushang@zhoushangdeMacBook-Air travel_guides % find berlitz1 -size +5M
`

Using `-size` option to see if there exist file that is larger than the size given. Here we have no file that is larger than 5 mb.