1. git branch -a

2. git branch -r

3. git checkout 

   ```shell
   git add .
   git commit -m "test" 
   git branch test（创建分支）
   
   git checkout test （切换分支）
   git push origin test 
   git push origin --delete test (删除远程分支)
   ```
   
   ```
   QUERY_RULES = [
       'title="中央" || title="中国" || title="国家" || title="航海" || body="fileId=485733195602" || body="fileId=485737359171" || body="ownerId=484387821692" || body="ownerId=484398248483" || body="saved from url=(0047)https" || body="mimg.127.net/p/images/favicon.ico" || body="mail.qq.com/favicon.ico" || title="网易网盘" || title="中转站" || title="中核" || title="中铁" || title="中航" || title="航空" || title="航天" || title="政府" || title="委员会" || title="工业集团" || title="中华人民共和国" || title="研究院" || title="北京天坛生物制品股份" || title="浙江能源集团" || title="中远海运散货运输" || title="海通期货股份" || title="国投新疆罗布泊钾盐" || title="国投哈密风电" || title="中能建绿色建材" || title="中化国际（控股）股份"',
       'title="中交融资租赁" || title="上海振华重工（集团）股份" || title="中交第二航务工程局" || title="湖北能源集团" || title="东风汽车股份" || title="北奔重型汽车集团" || title="广东电网" || title="西安热工研究院" || title="大唐陕西发电" || title="中煤第一建设" || title="云南合和（集团）股份" || title="招银金融租赁" || title="国电长源电力股份" || title="东风汽车" || title="红云红河烟草（集团）" || title="国投云南大朝山水电" || title="红塔烟草（集团）" || title="云南中烟工业" || title="中交第一航务工程局" || title="三峡新能源公司" || title="中航通用飞机" || title="山西省信息产业技术研究院" || title="大唐山西发电" || title="山西云时代政务云技术" || title="上海市气象局" || title="上海核工程研究设计院" || title="中远海运科技股份" || title="中移(上海)信息科技" || title="江苏中烟工业" || title="贵州省体育彩票管理中心" || title="中煤新集利辛发电" || title="中体彩彩票运营管理" || title="一汽解放汽车" || title="华电四川发电" || title="河北省水利厅" || title="金融"|| title="银行"|| title="保险"|| title="医疗"|| title="教育"|| title="支付"'
   ]
   ```

1. 字典读取 这样可以更省内存
2. 代码要纯粹

# Linux

```shell
ls -al # 可以查看被隐藏的文件
echo $HOME # 可以查看变量值HOME代替的路径
# 查看.vimrc的位置
# 在vim中使用命令 :version
```

