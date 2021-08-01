1.hashMap.containsKey(value)最好情况便是O(1)，最坏情况是O(n)

2.前端传参到后端，值多带一个逗号原因：多次传同一个值

3.windows查看端口号(6397)对应的进程 netstat -aon|findstr "6379"

4.使用Bigdecimal的BigDecimal(String)构造器的变量在进行运算的时候不会发生精度丢失，其他都会发生精度丢失

5.@Autowired注入对象为空，可能的原因：在所有使用dao的地方包括service都需要@Autowired注入

`@Component`
`@Transactional`
`public class XXService {`
    `private Logger logger = LoggerFactory.getLogger(getClass());    
    @Autowired`
    `private XXDao xxDao;      
    public void add(XX xxl) {        
        logger.debug("进入XXService.add(XX xx)方法");`
        `xxDao.save(xx); //此处报空指针,原因是xxDao为null`
`}`

`@RestController`
`@RequestMapping(value = "/xxx/xx")`
`public class XXController {`
    `Logger logger = LoggerFactory.getLogger(getClass());`
    `private XXService xxService = new XXService();//此处选择了实例化，没有用@Autowired`
      `.....`
`}`

6.图片地址要做预调整，不然APP需要转义带中文的url

7.windows 查看 端口连接数`netstat -an |find /c ":80"`