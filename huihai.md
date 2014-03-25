##惠海接口
###1.惠海消息接口
####1.1惠海接收消息接口
    url:http://v.home3d.cn/home/capi/space.php?do=message&uid=4821

>本url为测试样例   
>其中需要改变的是uid后的数值，即当前公众号在惠海平台的id标识，这个可以在官网查询到

返回数据     

	{
    "code": 0,
    "data": {
        "list": [
            {
                "id": "6",
                "viewuid": "4822",
                "fakeid": "22479295",
                "message": "神马情况",
                "uid": "4821",
                "dateline": "",
                "name": "huixiang",
                "viewname": "钟魏"
            }
        ],
        "count": "1"
    },
    "msg": "rest_success",
    "action": "rest_success"
	}
>code:状态码，0为成功，其它为失败   
>id:其消息id标识      
>viewuid:微信用户在惠海平台id标识   
>fakeid:微信用户微信平台标识   
>message:微信用户消息内容   
>uid:公众帐号惠海平台标识   
>dateline:发布时间   
>name：公众帐号账号名称   
>viewname：微信用户帐号名称   

####1.2惠海发送消息接口
	url:http://v.home3d.cn/home/capi/space.php?do=tomessage&uid=4821&viewuid=4822&message=123
>本url为测试样例    
>其中uid，viewuid，message为需要填写的参数    
>uid:公众帐号在惠海平台的id标识   
>viewuid:普通微信用户在惠海平台的id标识，这个可以从接收消息接口查询到    
>message:想要发送的内容

返回数据

	{
		    "code": 1,
		    "data": [],
		    "msg": "发送成功",
		    "action": "发送成功"
		}
>msg:返回消息，分为发送成功与发送失败2种情况

<br/><br/><br/>
<h2>2014/3/18更新</h2>
####1.3惠海公众号用户信息接口
	url:http://v.home3d.cn/home/capi/space.php?do=member
	url:http://v.home3d.cn/home/capi/space.php?do=member&username=huihai
	url:http://v.home3d.cn/home/capi/space.php?do=member&userId=gh_e1a171fe18d3

>分两种情况：   
>1，如果是想获取全平台用户，就是用第一种url，后缀不加上参数username   
>2，第二种url是对某个公众帐号的用户进行获取，后缀username上只需带上你在惠海平台注册的公众号账号即可。
>3，第三种url是对某个公众帐号的wxkey进行获取，后缀uuserID上只需带上你在获取的wxkey即可。

返回数据（第二种情况）：
    
    {
    "code": 0,
    "data": {
        "user": [
            {
                "uid": "4846",
                "username": "oYcLvjuQt4TsCycJ4VSNFXGq2V0Q",
                "name": "Panyuting",
                "dateline": "1395042819",
                "wxkey": "oYcLvjuQt4TsCycJ4VSNFXGq2V0Q",
                "fakeid": "1611944200",
                "fatheruid": "4829"
            },
            {
                "uid": "4845",
                "username": "oYcLvjrlv5Ufcide4GYanSLMcG-0",
                "name": "",
                "dateline": "1395041997",
                "wxkey": "oYcLvjrlv5Ufcide4GYanSLMcG-0",
                "fakeid": "11941715",
                "fatheruid": "4829"
            },
            {
                "uid": "4838",
                "username": "oYcLvjv5SHK8cpDjr1Ek1xf6izDI",
                "name": "毛毛",
                "dateline": "1394503826",
                "wxkey": "oYcLvjv5SHK8cpDjr1Ek1xf6izDI",
                "fakeid": "521858695",
                "fatheruid": "4829"
            },
            {
                "uid": "4834",
                "username": "oYcLvjrS5Yzz2wI6x1Nqh17d0kCc",
                "name": "赖涛",
                "dateline": "1394363755",
                "wxkey": "oYcLvjrS5Yzz2wI6x1Nqh17d0kCc",
                "fakeid": "1093005580",
                "fatheruid": "4829"
            },
            {
                "uid": "4833",
                "username": "oYcLvjga-M4z3afeGetSR5H2vB0k",
                "name": "龚国龙  Lonnie",
                "dateline": "1394285674",
                "wxkey": "oYcLvjga-M4z3afeGetSR5H2vB0k",
                "fakeid": "1591015205",
                "fatheruid": "4829"
            },
            {
                "uid": "4832",
                "username": "oYcLvji_NkztLZ9CYCVOOUrbymhw",
                "name": "Jie",
                "dateline": "1394269137",
                "wxkey": "oYcLvji_NkztLZ9CYCVOOUrbymhw",
                "fakeid": "185877120",
                "fatheruid": "4829"
            },
            {
                "uid": "4831",
                "username": "oYcLvjhug_Csd_hbelhmTVvj9RXk",
                "name": "陈逸龙",
                "dateline": "1394266179",
                "wxkey": "oYcLvjhug_Csd_hbelhmTVvj9RXk",
                "fakeid": "657032621",
                "fatheruid": "4829"
            }
        ],
        "count": 7
    },
    "msg": "rest_success",
    "action": "rest_success"
    }
>msg:返回消息，分为发送成功与发送失败2种情况  
>uid:用户id标识  
>username:用户注册时是使用微信标识进行注册，故此项可忽略  
>name:通过获取用户的微信名称进行实名  
>dateline:用户注册时间戳  
>wxkey:用户针对单一账号微信标识，但用户关注不同公众号，他的wxkey也会不同  
>fakeid:用户的全平台微信标识，最好以这个为标识基准  
>fatheruid:用户关注的公众帐号的uid  


<br/>
备注：另外，对于从菜单点击的URL到微商城的会话中，要把个人微信号和公众号传递到微商城，现在在url上新增了一个参数fwxkey，fwxkey上带的就是公众号的标识了。同时，wxkey就是个人微信号。<br/><br/>需要注意的是，其实跟之前的url是没什么变化的，只是我在每一个url上加上了一个新的参数，fwxkey，这个参数就是公众号的标识，而原来的wxkey还是个人微信号。请知悉
--------------------------------------------------------------------------------------------------
    