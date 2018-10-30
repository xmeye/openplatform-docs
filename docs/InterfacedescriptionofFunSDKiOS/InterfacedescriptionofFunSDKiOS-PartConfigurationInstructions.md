## 用URL初始化报警消息订阅

```
typedef struct SMCInitInfo
{
    char user[512];
    char password[512];
    char token[256]; // Google报警需要256， 多个报警订阅用&&连接
    int language;       // EMSGLANGUAGE
    int appType;        // EAPPTYPE
    char szAppType[64]; // XXXXXX
}SMCInitInfo;


SMCInitInfo info = {0};

    STRNCPY(info.token, tokenChar);
    strcpy(info.user, userName);
    strcpy(info.password, password);
    info.language = language;

#ifdef DEBUG
    pushType = DevelopmentType;
#else
    pushType = ProductionType;
#endif
    info.appType  =  pushType;

    STRNCPY(info.szAppType, [@"Third:http://xxxxx xxxx" UTF8String]);//(例：Third:http(s)://xmey.net:80/xxx/xxx 或 Third:ip:80 中间用“:”做分隔符)

    NSDictionary *infoDictionary = [[NSBundle mainBundle]infoDictionary];
    NSString *bundleIdentifiler = [infoDictionary objectForKey:@"CFBundleIdentifier"];

    STRNCPY(info.szAppType, [bundleIdentifiler UTF8String]);

    MC_Init(SELF, &info, 0);

```












