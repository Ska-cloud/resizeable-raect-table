## 说明
**必须要指定Columns的宽度**<br />
通过react-resizeable库给antd的table的cell加方法，以达到可以拖拽改变列宽的目的。<br />
antd3官方是给出了基于react-resizeable的方法，但是存在列多时卡顿的问题所以被取消了
## example
```typescript
const columns: ResizeTableColumnsType = [
      {
        width: 50,
        resizable: false,
];
const dataSource: object[] = [
  xxx
] 

return (
<ResizeTable
          size="small"
          columns={columns}
          dataSource={ dataSource }
          pagination={{ pageSize: 100 }}
        />
)
```
## feature
本人是做后端的，所以并不熟悉前端代码，能力有限，目前也在尝试能解决卡顿问题，希望有大佬能帮忙一起解决<br />
卡顿问题，个人感觉是因为实时渲染所以频率太高而导致的，所以我尝试使用onResizeStop钩子函数去拿到最后状态，<br />
在拖拽事件结束以后再setColumns，但是如果不实时渲染不能正确拿到最后状态的宽，希望有大佬帮忙解决。
