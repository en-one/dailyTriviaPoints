## Go 常用时间处理





- 比较两个时间相差几天

> ```go
> func getDiffDays(t1, t2 time.Time) int {
> 	t1 = time.Date(t1.Year(), t1.Month(), t1.Day(), 0, 0, 0, 0, time.Local)
> 	t2 = time.Date(t2.Year(), t2.Month(), t2.Day(), 0, 0, 0, 0, time.Local)
> 
> 	return int(t1.Sub(t2).Hours() / 24)
> }
> ```



- 获取时间的零点时间戳

> ```Go
> func getCurDayZeroTimeStamp(t time.Time) (int64, error) {
>    timeStr := t.Format("2006-01-02")
>    zeroTime, err := time.ParseInLocation("2006-01-02", timeStr, time.Local)
>    if err != nil {
>       return 0, err
>    }
>    return zeroTime.Unix(), nil
> }
> ```
>
> 
