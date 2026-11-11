---
created: 2026-11-10 21:17
modified: 2026-11-10 21:49
---
```dataviewjs
dv.span("")

const calendarData = {
    year: 2026,
    intensityScaleEnd: 200,
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: [],
    showCurrentDayBorder: true,
}

for(let page of dv.pages('"daily note"').where(p=>p.pushups)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.pushups
        
        
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```


