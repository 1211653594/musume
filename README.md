# 博物馆APP

## 加值宣言
- 不论是移动不便的身障人士，还是难以在一处长期停留的多动用户，也能在博物馆中体验良好的观赏感。

## 核心价值
- 帮助特殊群体找到一条最快到达他们所需目的地的道路。
- 让特殊群体省去打字时间，将他们的语音转化为文字，帮助他们将内容输入到搜索框。

## 需求背景
- 作为征集、典藏、陈列和研究代表自然和人类文化遗产的实物的场所，博物馆针对全人类开放。然而，在大众之中，某些特殊群体的存在让许多针对正常人开发的功能、或是服务变得略有欠缺。比如博物馆，即便它对大众开放，它也没有一些具体的功能可以帮助到特殊群体，对移动不便的身障人士或难以保持不动的多动用户来说，即便现代的博物馆多了很多服务和功能，也和以往没有太大的不同。

## 需求目的
- 

## 需要的API
- 高德API中的路径规划。
- 百度AI开放平台中的语音识别。

## API加值主张
- 高德路径规划：一套以HTTP形式提供的步行、公交、驾车查询及行驶距离计算接口，返回JSON 或 XML格式的查询数据，用于实现路径规划功能的开发。 用户在输入自己的要查询的位置后，该API可返回相应的最佳路径，让用户找到最佳的行驶路径。
- 百度语音识别：将音频流实时识别为文字，并返回每句话的开始和结束时间。

## APP价值主张
- 用户通过实时语音输入，可省去手动输入的麻烦与不便，将可能浪费在手动输入上的成本和时间花在其他事情上。
- 用户在搜到相应的路径后，可以准确无误地找到自己的目的地。省去了寻问的不便，且不会走错路。

## APP价值核心
- 用户在语音输入时可解放双手，说话内容实时展示在屏幕上，双手可做其他事情（如推轮椅）。
- 用户无需展现地图的场景下，进行线路查询，如以线路结果页形式展现换乘方案。

## 针对用户
- 身障人士。
- 不喜欢博物馆想要快速浏览完博物馆的多动人士。

## 用户痛点
- 想要好好浏览博物馆，却因为身体情况无法舒心地观赏，找不到最佳路线，或者觉得手动输入文字十分费力。
- 想要快速离开博物馆，受不了里面的安静，无法舒展身心，想快速看完里面的文物然后离开。

## 产品原型

## 产品结构图

## API的运用
### 高德API路径规划
- 调用方法：申请”Web服务API”密钥（Key）；拼接HTTP请求URL，第一步申请的Key需作为必填参数一同发送；接收HTTP请求返回的数据（JSON或XML格式），解析数据。
- 注意：如无特殊声明，接口的输入参数和输出数据编码全部统一为UTF-8；此API不知针对步行，但根据使用场景的大小，这里只做了步行路径规划的示例。
- 请求方式：GET。
- 请求URL：https://restapi.amap.com/v3/direction/walking?parameters
- 使用示例：
```
https://restapi.amap.com/v3/direction/walking?origin=116.434307,39.90909&destination=116.434446,39.90816&key=<用户的key>
```
- 返回示例：
```
{
"status" :
"1",
"info" :
"ok",
"infocode" :
"10000",
"count" :
"1",
"route" :
{
"origin" :
"116.481028,39.989643",
"destination" :
"116.434446,39.90816",
"paths" :
[
"0" :
{
"distance" :
"11153",
"duration" :
"8922",
"steps" :
[
"0" :
{
"instruction" :
"向南步行16米左转",
"orientation" :
"南",
"road" :
[ ],
"distance" :
"16",
"duration" :
"13",
"polyline" :
"116.480885,39.989371;116.480907,39.989353;116.48089,39.989227",
"action" :
"左转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"1" :
{
"instruction" :
"向东南步行282米向右前方行走",
"orientation" :
"东南",
"road" :
[ ],
"distance" :
"282",
"duration" :
"226",
"polyline" :
"116.480885,39.989223;116.480933,39.989201;116.480933,39.989201;116.481428,39.98888;116.481428,39.98888;116.481467,39.988859;116.481467,39.988859;116.483381,39.987604;116.483381,39.987604;116.483411,39.987582",
"action" :
"向右前方行走",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"2" :
{
"instruction" :
"向南步行19米右转",
"orientation" :
"南",
"road" :
[ ],
"distance" :
"19",
"duration" :
"15",
"polyline" :
"116.483411,39.987578;116.483464,39.987405",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"3" :
{
"instruction" :
"向西南步行291米左转",
"orientation" :
"西南",
"road" :
[ ],
"distance" :
"291",
"duration" :
"233",
"polyline" :
"116.483464,39.9874;116.483424,39.987357;116.483424,39.987357;116.483234,39.987296;116.48263,39.986753;116.48263,39.986753;116.482057,39.986233;116.482027,39.986089;116.482027,39.986089;116.48135,39.985486;116.48135,39.985486;116.481289,39.985434",
"action" :
"左转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"4" :
{
"instruction" :
"向东南步行166米右转",
"orientation" :
"东南",
"road" :
[ ],
"distance" :
"166",
"duration" :
"133",
"polyline" :
"116.481285,39.98543;116.481411,39.985339;116.481411,39.985339;116.481619,39.985299;116.482153,39.984944;116.482153,39.984944;116.482513,39.984718;116.482513,39.984718;116.482678,39.984601;116.482726,39.98447",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"5" :
{
"instruction" :
"沿京密路向西南步行2961米向左前方行走",
"orientation" :
"西南",
"road" :
"京密路",
"distance" :
"2961",
"duration" :
"2369",
"polyline" :
"116.482726,39.984466;116.482591,39.984336;116.482591,39.984336;116.4825,39.984258;116.4825,39.984258;116.481662,39.983494;116.481662,39.983494;116.481233,39.983086;116.479653,39.981667;116.479653,39.981667;116.478672,39.980794;116.47809,39.980269;116.47809,39.980269;116.478021,39.980204;116.478021,39.980204;116.477982,39.980165;116.477982,39.980165;116.477205,39.979436;116.477205,39.979436;116.476853,39.979115;116.476853,39.979115;116.476719,39.978997;116.476719,39.978997;116.476055,39.97839;116.476055,39.97839;116.475039,39.977478;116.475039,39.977478;116.475,39.977448;116.475,39.977448;116.47388,39.976428;116.47388,39.976428;116.473286,39.975894;116.473286,39.975894;116.472765,39.97543;116.472765,39.97543;116.472383,39.975117;116.472383,39.975117;116.471315,39.974149;116.471315,39.974149;116.469544,39.972526;116.469089,39.972122;116.469089,39.972122;116.468281,39.971402;116.468281,39.971402;116.466523,39.969805;116.466523,39.969805;116.465373,39.96875;116.465373,39.96875;116.464952,39.968372;116.464952,39.968372;116.464779,39.968212;116.464779,39.968212;116.464466,39.967934;116.464466,39.967934;116.462817,39.966432;116.462817,39.966432;116.462747,39.96638;116.462747,39.96638;116.460803,39.964601;116.460803,39.964601;116.460191,39.964049",
"action" :
"向左前方行走",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"6" :
{
"instruction" :
"步行10米右转",
"orientation" :
[ ],
"road" :
[ ],
"distance" :
"10",
"duration" :
"8",
"polyline" :
"116.460187,39.964045;116.460286,39.963984",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"1"
},
"7" :
{
"instruction" :
"沿京密路向西南步行715米直行",
"orientation" :
"西南",
"road" :
"京密路",
"distance" :
"715",
"duration" :
"572",
"polyline" :
"116.460278,39.963984;116.460117,39.963828;116.460117,39.963828;116.458016,39.961927;116.458016,39.961927;116.457977,39.961901;116.457977,39.961901;116.457444,39.961419;116.457444,39.961419;116.457391,39.961372;116.457391,39.961372;116.456736,39.960829;116.456736,39.960829;116.456185,39.960447;116.456185,39.960447;116.455569,39.960109;116.455569,39.960109;116.454805,39.959744;116.454614,39.959627;116.454379,39.959431",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"8" :
{
"instruction" :
"沿香河园路向西南步行402米向左前方行走",
"orientation" :
"西南",
"road" :
"香河园路",
"distance" :
"402",
"duration" :
"322",
"polyline" :
"116.454375,39.959427;116.453624,39.958754;116.453624,39.958754;116.453507,39.958641;116.453507,39.958641;116.453125,39.958303;116.453125,39.958303;116.452999,39.95819;116.452999,39.95819;116.452478,39.957739;116.452478,39.957739;116.451311,39.956654",
"action" :
"向左前方行走",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"9" :
{
"instruction" :
"沿香河园路向西南步行1763米右转",
"orientation" :
"西南",
"road" :
"香河园路",
"distance" :
"1763",
"duration" :
"1410",
"polyline" :
"116.451306,39.956649;116.451272,39.956549;116.451272,39.956549;116.45122,39.956471;116.45122,39.956471;116.451098,39.956354;116.451098,39.956354;116.451059,39.956311;116.451059,39.956311;116.450686,39.956007;116.450686,39.956007;116.450143,39.955521;116.450143,39.955521;116.450009,39.955399;116.450009,39.955399;116.449848,39.955247;116.449848,39.955247;116.44974,39.955161;116.44974,39.955161;116.449314,39.954783;116.449314,39.954783;116.448559,39.954084;116.448559,39.954084;116.44849,39.954032;116.44849,39.954032;116.447856,39.953537;116.447856,39.953537;116.447773,39.953472;116.447773,39.953472;116.447192,39.953051;116.447192,39.953051;116.446055,39.952214;116.446055,39.952214;116.445994,39.952166;116.445994,39.952166;116.44546,39.951771;116.44546,39.951771;116.445078,39.951497;116.444878,39.95148;116.444878,39.95148;116.444766,39.951393;116.444766,39.951393;116.444193,39.951016;116.444193,39.951016;116.443772,39.950703;116.443772,39.950703;116.442613,39.94987;116.442613,39.94987;116.442248,39.949605;116.442248,39.949605;116.441285,39.948906;116.441285,39.948906;116.441202,39.948841;116.441202,39.948841;116.440686,39.948442;116.440686,39.948442;116.440547,39.948338;116.440547,39.948338;116.440004,39.947873;116.440004,39.947873;116.439492,39.947444;116.439266,39.947231;116.439036,39.946984;116.439036,39.946984;116.438793,39.946714;116.438793,39.946714;116.438685,39.946584;116.438685,39.946584;116.438637,39.946532;116.438637,39.946532;116.438572,39.94645;116.438572,39.94645;116.438503,39.946367;116.438503,39.946367;116.438342,39.946172;116.438342,39.946172;116.43809,39.945855;116.437912,39.945599;116.437912,39.945599;116.437439,39.94487",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"10" :
{
"instruction" :
"沿香河园路向西步行293米左转",
"orientation" :
"西",
"road" :
"香河园路",
"distance" :
"293",
"duration" :
"234",
"polyline" :
"116.437435,39.944865;116.437326,39.944844;116.437326,39.944844;116.434961,39.944839;116.434961,39.944839;116.434831,39.944839;116.434831,39.944839;116.434444,39.944839;116.434444,39.944839;116.434006,39.944835",
"action" :
"左转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"11" :
{
"instruction" :
"沿东直门北大街向南步行62米向左前方行走",
"orientation" :
"南",
"road" :
"东直门北大街",
"distance" :
"62",
"duration" :
"50",
"polyline" :
"116.434002,39.944831;116.433976,39.944271",
"action" :
"向左前方行走",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"12" :
{
"instruction" :
"步行101米右转",
"orientation" :
[ ],
"road" :
[ ],
"distance" :
"101",
"duration" :
"81",
"polyline" :
"116.433971,39.944266;116.434019,39.944266;116.434019,39.944266;116.434006,39.944167;116.434006,39.944167;116.433932,39.944167;116.433932,39.944167;116.43355,39.944171;116.43355,39.944171;116.43339,39.944175;116.43339,39.944175;116.43339,39.943898;116.43339,39.943898;116.433464,39.943898",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"4"
},
"13" :
{
"instruction" :
"沿东直门北大街向南步行310米直行",
"orientation" :
"南",
"road" :
"东直门北大街",
"distance" :
"310",
"duration" :
"248",
"polyline" :
"116.433464,39.943893;116.433485,39.94332;116.433485,39.94332;116.433516,39.942665;116.433516,39.942665;116.433559,39.941667;116.433559,39.941667;116.433585,39.941089",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"14" :
{
"instruction" :
"沿东直门南大街向南步行741米",
"orientation" :
"南",
"road" :
"东直门南大街",
"distance" :
"741",
"duration" :
"593",
"polyline" :
"116.433585,39.941085;116.433615,39.940486;116.433615,39.940486;116.433655,39.939614;116.433655,39.939614;116.433655,39.938828;116.433655,39.938828;116.433685,39.938164;116.433685,39.938164;116.433707,39.93783;116.433707,39.93783;116.433707,39.937457;116.433707,39.937457;116.43372,39.937161;116.43372,39.937161;116.433746,39.93671;116.433746,39.93671;116.433759,39.936324;116.433759,39.936324;116.433767,39.936133;116.433767,39.936133;116.433806,39.935677;116.433806,39.935677;116.433867,39.934366;116.433867,39.934366;116.433867,39.934353",
"action" :
[ ],
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"15" :
{
"instruction" :
"沿东直门南大街向南步行321米直行",
"orientation" :
"南",
"road" :
"东直门南大街",
"distance" :
"321",
"duration" :
"257",
"polyline" :
"116.433867,39.934349;116.433928,39.933125;116.433928,39.933125;116.433928,39.933112;116.433928,39.933112;116.433958,39.932227;116.433958,39.932227;116.433971,39.931771;116.433932,39.931454",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"16" :
{
"instruction" :
"沿朝阳门北大街向南步行517米向右前方行走",
"orientation" :
"南",
"road" :
"朝阳门北大街",
"distance" :
"517",
"duration" :
"414",
"polyline" :
"116.433928,39.93145;116.433958,39.931107;116.433958,39.931107;116.433958,39.931063;116.433958,39.931063;116.433967,39.930838;116.433967,39.930838;116.433967,39.930786;116.433967,39.930786;116.433971,39.93066;116.433971,39.93066;116.433997,39.930226;116.433997,39.930226;116.434032,39.929553;116.434032,39.929553;116.434032,39.929497;116.434032,39.929497;116.43408,39.928555;116.43408,39.928555;116.434089,39.928294;116.434089,39.928294;116.434119,39.927539;116.434119,39.927539;116.434158,39.926749",
"action" :
"向右前方行走",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"17" :
{
"instruction" :
"沿朝阳门桥步行231米左转",
"orientation" :
[ ],
"road" :
"朝阳门桥",
"distance" :
"231",
"duration" :
"185",
"polyline" :
"116.434158,39.926745;116.434093,39.926502;116.434062,39.926328;116.434062,39.926328;116.434036,39.926224;116.434036,39.926037;116.43408,39.92559;116.43408,39.92559;116.43408,39.925516;116.43408,39.925516;116.434097,39.925061;116.434093,39.924753;116.434093,39.924753;116.434193,39.924761",
"action" :
"左转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"18" :
{
"instruction" :
"步行36米右转",
"orientation" :
[ ],
"road" :
[ ],
"distance" :
"36",
"duration" :
"29",
"polyline" :
"116.434193,39.924761;116.434193,39.925017;116.434284,39.925017",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"20"
},
"19" :
{
"instruction" :
"沿朝阳门北大街向南步行295米直行",
"orientation" :
"南",
"road" :
"朝阳门北大街",
"distance" :
"295",
"duration" :
"236",
"polyline" :
"116.434284,39.925017;116.434323,39.923911;116.434323,39.923911;116.434323,39.92388;116.434323,39.92388;116.434353,39.923273;116.434362,39.922578;116.434362,39.922578;116.434371,39.922348",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"20" :
{
"instruction" :
"沿朝阳门南大街向南步行726米直行",
"orientation" :
"南",
"road" :
"朝阳门南大街",
"distance" :
"726",
"duration" :
"581",
"polyline" :
"116.434371,39.922344;116.434366,39.922001;116.434366,39.922001;116.434379,39.921563;116.434379,39.921563;116.434379,39.921519;116.434379,39.921519;116.434401,39.921094;116.434401,39.921094;116.434414,39.920677;116.434414,39.920677;116.434431,39.920304;116.434431,39.920304;116.434444,39.920052;116.434444,39.920052;116.43447,39.919544;116.43447,39.919544;116.434475,39.919453;116.434475,39.919453;116.434505,39.918633;116.434505,39.918633;116.434523,39.918451;116.434523,39.918451;116.434536,39.917982;116.434536,39.917982;116.434562,39.917244;116.434562,39.917244;116.434601,39.916497;116.434601,39.916497;116.434622,39.916063;116.434622,39.916063;116.434631,39.915764;116.434631,39.915764;116.434635,39.915703",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"21" :
{
"instruction" :
"沿建国门北大街向南步行818米直行",
"orientation" :
"南",
"road" :
"建国门北大街",
"distance" :
"818",
"duration" :
"654",
"polyline" :
"116.434635,39.915699;116.434644,39.91556;116.434644,39.91556;116.434644,39.915417;116.434644,39.915417;116.434661,39.915065;116.434661,39.915065;116.434661,39.914952;116.434661,39.914952;116.434696,39.914284;116.434696,39.914284;116.434757,39.913555;116.434757,39.913555;116.434757,39.91349;116.434757,39.91349;116.434774,39.913177;116.434774,39.913177;116.434787,39.913025;116.434787,39.913025;116.434796,39.912839;116.434796,39.912839;116.434822,39.912274;116.434822,39.912274;116.434822,39.912248;116.434822,39.912248;116.434852,39.911784;116.434852,39.911784;116.434874,39.91122;116.434874,39.91122;116.434918,39.910109;116.434918,39.910109;116.434965,39.909054;116.434965,39.909054;116.434931,39.908932;116.434887,39.908867;116.434887,39.908867;116.434818,39.908655;116.434826,39.908424;116.434883,39.908303",
"action" :
"直行",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"22" :
{
"instruction" :
"沿建国门南大街向东南步行29米右转",
"orientation" :
"东南",
"road" :
"建国门南大街",
"distance" :
"29",
"duration" :
"23",
"polyline" :
"116.434883,39.908299;116.434974,39.908194;116.435009,39.908077",
"action" :
"右转",
"assistant_action" :
[ ],
"walk_type" :
"0"
},
"23" :
{
"instruction" :
"步行48米到达目的地",
"orientation" :
[ ],
"road" :
[ ],
"distance" :
"48",
"duration" :
"38",
"polyline" :
"116.435009,39.908073;116.434449,39.908073",
"action" :
[ ],
"assistant_action" :
"到达目的地",
"walk_type" :
"0"
}
]
}
]
}
}
```

### 百度语音识别
- 调用方法：使用appKey secretKey 访问 https://openapi.baidu.com 换取 token；选择一种HTTP POST 请求格式；填写参数。
- 注意：如果您的音频在本地，需要将音频数据放在body中。（推荐方式） 音频在本地，有JSON和raw两种方式提交。这两种提交方式，均不是浏览器表单的提交。
- 请求方式：POST。
- 请求URL：http://vop.baidu.com/server_api

## 使用比较分析
### 高德路径规划
- 在众多API开放平台中，除了高德外，目前国内确实也有其他的开放平台具有路径规划功能（如WeDrive）。但考虑到了权威性、可靠性、以及传播性，本项目使用高德的路径规划API。高德的路径规划API不仅可以供用户免费使用，每天使用的次数还不受限制。

### 百度语音识别
- 在国内，具有语音识别API的开放平台不止百度一家。然而，在经过调查和帅选后，本项目最终还是决定使用百度的语音识别API。一方面，在拥有语音识别的API中，百度公司是目前最具有权威性和可靠性的API开放平台；另一方面，百度的语音识别API并不收费，且每天调用的数量无限制。综上所述，本项目使用百度的语音API。

## 清单

[百度语音API](https://ai.baidu.com/tech/speech)