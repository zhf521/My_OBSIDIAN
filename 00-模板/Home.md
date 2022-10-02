---
banner: "https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/主页导航头图.png"
cssclass: fullwidth,noyaml,noscroll,myhome
---

%% 动画猫 %%
```jsx::AnimationCat
```






%% --文字版天气加图标--开始 %%
>[!note|noborder banner]  &nbsp;
>```dataviewjs
let setting = {};
let history = Object.assign(JSON.parse(await app.vault.adapter.read(".obsidian/.diary-stats")));
let today = moment().format("YYYY-MM-DD");
if (history.hasOwnProperty(today))
{let weather=history[today].weather;
let todayweather = weather[0];
setting.iconDay =  weather[0].iconDay;
setting.windSpeedDay =  weather[0].windSpeedDay;
setting.windSpeedNight =  weather[0].windSpeedNight;
await dv.view("00-模板/script/dv_weatherSvg",setting)
let desc = ` <%+ tp.date.now("A好，今天是YYYY年MM月Do dddd") %> ，${todayweather.city} ${todayweather.textDay}， ${todayweather.tempMin}~${todayweather.tempMax}℃  ${todayweather.air} ${todayweather.windydesc} [[最近天气查询|✈️]] \n云朵充盈了${todayweather.cloud}%的天空。今天月亮是这样的：${todayweather.moonPhase.replace(/[\u4e00-\u9fa5]/g,"")}`;
dv.paragraph(desc);
}
>```
%% ---文字版天气加图标--结束 %%

%% 历史记录 %%
```ActivityHistory
/
```
%% 标签云 %%
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: WordCloud

#-----------------#
#- chart data    -#
#-----------------#
data: |
    dataviewjs:
    return (() => {
        const tags = this.app.metadataCache.getTags();
        console.dir(tags);
        let dataArray = [];
        Object.keys(tags).forEach(key => dataArray.push({
            tag:key.replace("#",""),
            count:tags[key]
        }));

        return dataArray.filter(p => !p.tag.includes("MOC"));

    })();

#-----------------#
#- chart options -#
#-----------------#
options:
  wordField: "tag"
  weightField: "count"
  colorField: "count"
  wordStyle:
    rotation: 0
  enableSearchInteraction:
    operator: tag
```

