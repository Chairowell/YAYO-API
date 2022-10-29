# YAYO-API
收集世界各地遍布的野生API

# biu.moe API

接口

```json
https://web.biu.moe/Song/playSID/sid/{sid}
```

用途

1. 获取音乐url（.m4a格式）
2. 获取音乐信息（歌曲名，制作人，唱片集）

请求参数

| 参数名称 | 请求方式 | 参数类型 | 描述   |
| -------- | -------- | -------- | ------ |
| sid      | GET      | int      | 歌曲id |

返回参数

| 参数                 | 参数类型 | 说明         |
| -------------------- | -------- | ------------ |
| `['urlinfo']['url']` | url      | 歌曲文件链接 |
| `['info'][0]`        | int      | 歌曲ID       |
| `['info'][1]`        | str      | 歌曲名       |
| `['info'][2]`        | str      | 制作人       |
| `['info'][3]`        | str      | 唱片集       |
| `['status']`         | boolean  | 请求状态     |
| `['error']`          | str      | 错误问题     |

示例

```json
https://web.biu.moe/Song/playSID/sid/41490
```

返回体

```json
// OK
{
  "urlinfo": {
    "url": "https://can.biu.moe/v2/0/241490.m4a?e=1667014140&tk=efde8387144b9b3f22190add6d94ea7c&moehash=2333800",
    "et": "1667014140"
  },
  "info": [
    "41490",
    "黄昏時のレイライン～from A Clockwork Ley-Line～",
    "KIYO",
    "水月陵 ボーカルコレクション 1 / Ryo Mizutsuki Vocal Collection 1",
    "122",
    "1",
    "0",
    "16"
  ],
  "status": true
}
// ERROR
{
  "error": "歌曲不存在",
  "status": false
}
```



接口

```json
https://web.biu.moe/Song/getCover/sid/{sid}
https://web.biu.moe/Song/showCover/sid/{sid}
```

用途

1. 获取音乐封面

请求参数

| 参数名称  | 请求方式 | 参数类型 | 描述     |
| --------- | -------- | -------- | -------- |
| sid       | GET      | int      | 歌曲id   |
| getCover  | GET      | str      | 返回json |
| showCover | GET      | str      | 返回图片 |

返回参数

| 参数         | 参数类型 | 说明         |
| ------------ | -------- | ------------ |
| `['url']`    | url      | 歌曲封面链接 |
| `['status']` | boolean  | 请求状态     |

示例

```json
https://web.biu.moe/Song/getCover/sid/41490
```

返回体

```json
// OK
{
  "url": "https://biu.moe/Public/img/biu.png",
  "status": true
}
// ERROR
{
  "status": false
}
```

