# 09 Hold Shift and Check Checkboxes

## 任务

实现类似于各大邮箱的 按住shift后点击 可进行的全选功能

[实现效果](https://miaolegemie.github.io/Javascript30/10%20-%20Hold%20Shift%20and%20Check%20Checkboxes/)

## 任务要点

1. 为所有 `input` 添加点击监听
2. 保留每次点击的 `input` 下标来为下次点击做判断
3. 如果点击时有按下 `shift` 键，且不是第一次进行点击，则获得上次点击和本次点击及中间的所有 `input`
4. 获取后则将这些 `input` 每个的 `checked` 换成和**上一次点击后的 `input` 的 `checked` 相同**

## 步骤
1. 为所有 `input` 添加点击监听
2. 保留每次点击的 `input` 下标来为下次点击做判断
3. 如果点击时有按下 `shift` 键，且不是第一次进行点击，则获得上次点击和本次点击及中间的所有 `input`
4. 获取后则将这些 `input` 每个的 `checked` 换成和**上一次点击后的 `input` 的 `checked` 相同**

## 注意事项

注意对比和作者完成的代码及效果的不同
