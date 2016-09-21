---
order: 0
title: APP型选项卡
---

多用于页面的内容区块，起着控制小范围内的大块内容的分组和隐藏，起着保持界面整洁的作用。

````jsx
import { TabBar } from 'antd-mobile';

const TabBarExample = React.createClass({
  getInitialState() {
    return {
      selectedTab: 'redTab',
      presses: 0,
    };
  },
  renderContent(pageText) {
    return (
      <div style={{ backgroundColor: 'white', height: '100%' }}>
        <div style={{ paddingTop: 60, textAlign: 'center' }}>你已点击“{pageText}” tab， 当前展示“{pageText}”信息</div>
      </div>
    );
  },
  render() {
    return (
      <TabBar
        unselectedTintColor="#949494"
        tintColor="#33A3F4"
        barTintColor="white"
      >
        <TabBar.Item
          title="生活"
          key="生活"
          icon={{ uri: 'https://zos.alipayobjects.com/rmsportal/XLdKiKAwDRXQNhC.png' }}
          selectedIcon={{ uri: 'https://zos.alipayobjects.com/rmsportal/iKfBQdGdTMubhXy.png' }}
          selected={this.state.selectedTab === 'blueTab'}
          onPress={() => {
            this.setState({
              selectedTab: 'blueTab',
            });
          }}
        >
          {this.renderContent('生活')}
        </TabBar.Item>
        <TabBar.Item
          icon={{ uri: 'https://zos.alipayobjects.com/rmsportal/UNQhIatjpNZHjVf.png' }}
          selectedIcon={{ uri: 'https://zos.alipayobjects.com/rmsportal/HLkBvJOKnmOfBPO.png' }}
          title="口碑"
          key="口碑"
          badge={1}
          selected={this.state.selectedTab === 'redTab'}
          onPress={() => {
            this.setState({
              selectedTab: 'redTab',
            });
          }}
        >
          {this.renderContent('口碑')}
        </TabBar.Item>
        <TabBar.Item
          icon={{ uri: 'https://zos.alipayobjects.com/rmsportal/EljxLrJEShWZObW.png' }}
          selectedIcon={{ uri: 'https://zos.alipayobjects.com/rmsportal/LWNaMdwAFSmYBFw.png' }}
          title="朋友"
          key="朋友"
          selected={this.state.selectedTab === 'greenTab'}
          onPress={() => {
            this.setState({
              selectedTab: 'greenTab',
            });
          }}
        >
          {this.renderContent('朋友')}
        </TabBar.Item>
        <TabBar.Item
          icon={{ uri: 'https://zos.alipayobjects.com/rmsportal/YWpPVCVOnJoCYhs.png' }}
          selectedIcon={{ uri: 'https://zos.alipayobjects.com/rmsportal/WadBBxOIZtDzsgP.png' }}
          title="我的"
          key="我的"
          selected={this.state.selectedTab === 'yellowTab'}
          onPress={() => {
            this.setState({
              selectedTab: 'yellowTab',
            });
          }}
        >
          {this.renderContent('我的')}
        </TabBar.Item>
      </TabBar>
    );
  },
});

ReactDOM.render(<TabBarExample />, mountNode);
````

````css
.demo-preview-item,
.am-tab-bar,
.am-tab-bar-content,
.am-tab-bar-tabpane {
  height: 100%;
}
````