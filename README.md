# BOTZONE MAHJONG LOCAL SIMULATOR

注意，整个操作模式基本和BOTZONE在线平台上相同，但是全部按照simple input的方式进行

在运行过程中进行的非法操作会被raise出来。

## Example

``` python
env = MahjongEnvironment()
env.reset()
while not env.isEnd():
    states = env.state()
    responses = []
    for x in states:
        responses.append((player[x[1]].make_action(x[0]),x[1]))
    env.step(responses)
```

这里的player你可以使用各种方式进行实现，比如用socket/pipe之类的就可以把player做到单独的文件里面了
