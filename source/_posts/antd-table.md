---
title: antd-table 使用笔记
date: 2018-04-18 20:59:53
tags:
---

> 最近项目在使用antd碰到了些坑这里记录下来 方便以后翻阅


目前使用了table组件 


```
<Table
              rowSelection={{
                selectedRowKeys,
                onChange: (selectedRowKeys, selectedRows) => {
                  console.log(selectedRowKeys);
                  this.setState({
                    selectedRowKeys,
                    selectedRows
                  });
                },
                selections: {
                  onSelection: this.onSelection
                },
                onSelectInvert: selectedRows => {
                  console.log(selectedRows);
                },
                getCheckboxProps: record => ({
                  defaultChecked: record.id
                })
              }}
              columns={[
                {
                  title: '报案号',
                  dataIndex: 'reportNo',
                  width: 80
                },
                {
                  title: '立案号',
                  dataIndex: 'registerNo',
                  width: 80
                },
                {
                  title: '结案时间',
                  dataIndex: 'closeTime',
                  width: 80
                },
                {
                  title: '结案提交人',
                  dataIndex: 'closeOperator',
                  width: 80
                },
                {
                  title: '下载状态',
                  dataIndex: 'stateDesc',
                  width: 80
                }
              ]}
              dataSource={dataList}
              pagination={false}
              rowKey={record => record.id}
            />
```

默认全选  defaultChecked: record.id

table 属性需要加  rowKey={record => record.id}  这样禁用的时候不糊






