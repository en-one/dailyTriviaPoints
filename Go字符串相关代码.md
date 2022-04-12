## Go 字符串


- 判断字符串里有几个数字，几个汉字

> ```go
> s1 := "我是汉字abcd123"
> var countHan int
>	var countNum int
>	for _, v := range s1 {
>		if unicode.Is(unicode.Han, v) {
>			fmt.Println("找到汉字")
>			countHan++
>		}
>		if unicode.Is(unicode.Number, v) {
>			fmt.Println("找到数字")
>			countNum++
>		}
>	}
>	fmt.Println(countHan)
>	fmt.Println(countNum)
> ```



- 字符串与int的转换

> ```Go
> string    => int         int, err := strconv.Atoi(string)
> string    => int64       int64, err := strconv.ParseInt(string, 10, 64)
> 
> int   => string           string := strconv.Itoa(int)
> int64 => string           string := strconv.FormatInt(int64,10)
> ```






