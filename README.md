# react-navigation-snippets
This extension will help to create react-navigation components just by typing the few words using visual code editor.
## Features
`nav-app`
```
import 'react-native-gesture-handler';
import * as React from 'react'
import {StyleSheet} from 'react-native'
import { NavigationContainer } from '@react-navigation/native';

const AppNav = () => {
    return (
        <NavigationContainer>
            {/* Rest of your app code */}
        </NavigationContainer>
    );
}
const styles = StyleSheet.create({});
export default AppNav;
```

`nav-app-redux`
```
import 'react-native-gesture-handler';
import * as React from 'react'
import {StyleSheet} from 'react-native'
import { NavigationContainer } from '@react-navigation/native';

//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const AppContainer = () => {
    return (
        <NavigationContainer>
            {/* Rest of your app code */}
        </NavigationContainer>
    );
}

const styles = StyleSheet.create({});

const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(AppContainer);
```

`nav-stack`
```
import * as React from 'react'
import {StyleSheet} from 'react-native'
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();
const StackNav = () => {
    return (
        <Stack.Navigator
            initialRouteName=""
            keyboardHandlingEnabled={true}
            mode={'card'} // option (modal)
            headerMode={'screen'} // option (screen, float, none)
        >
            <Stack.Screen
                name="Home"
                component={HomeScreen}
                options={
                    {
                        title: 'Title',
                        headerTitleAlign: 'center', // option (center, left) Defaults to center on iOS and left on Android.
                        headerStyle: {},
                        headerTitleStyle: {},
                        headerBackTitleStyle: {},
                        headerLeftContainerStyle: {},
                        headerTitleContainerStyle: {},
                        headerRightContainerStyle: {},
                        headerTintColor: '',
                        headerTransparent: false,
                        cardShadowEnabled: true,
                        cardOverlayEnabled: true, // Defaults to true on Android and false on iOS.
                        //headerStatusBarHeight: 0,
                        //headerBackground: settings => { return null },
                        //header: settings => { return null }, // React Element
                        //headerTitle:settings => { return null }, // React Element
                        //headerRight: settings => { return null }, // React Element
                        //headerLeft: settings => { return null }, // React Element
                        //headerBackImage: settings => { return null }, // React element
                        //headerBackTitle:'', // Title string used by the back button on iOS. Defaults to the previous scene's headerTitle
                        //headerBackTitleVisible:true,
                    }
                }
            />
        </Stack.Navigator>
    );
}
export default StackNav;
```

`nav-stack-redux`
```
import * as React from 'react'
import {StyleSheet} from 'react-native'
import { createStackNavigator } from '@react-navigation/stack';

//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const Stack = createStackNavigator();
const StackNav = () => {
    return (
        <Stack.Navigator
            initialRouteName=""
            keyboardHandlingEnabled={true}
            mode={'card'} // option (modal)
            headerMode={'screen'} // option (screen, float, none)
        >
            <Stack.Screen
                name="Home"
                component={HomeScreen}
                options={
                    {
                        title: 'Title',
                        headerTitleAlign: 'center', // option (center, left) Defaults to center on iOS and left on Android.
                        headerStyle: {},
                        headerTitleStyle: {},
                        headerBackTitleStyle: {},
                        headerLeftContainerStyle: {},
                        headerTitleContainerStyle: {},
                        headerRightContainerStyle: {},
                        headerTintColor: '',
                        headerTransparent: false,
                        cardShadowEnabled: true,
                        cardOverlayEnabled: true, // Defaults to true on Android and false on iOS.
                        //headerStatusBarHeight: 0,
                        //headerBackground: settings => { return null },
                        //header: settings => { return null }, // React Element
                        //headerTitle:settings => { return null }, // React Element
                        //headerRight: settings => { return null }, // React Element
                        //headerLeft: settings => { return null }, // React Element
                        //headerBackImage: settings => { return null }, // React element
                        //headerBackTitle:'', // Title string used by the back button on iOS. Defaults to the previous scene's headerTitle
                        //headerBackTitleVisible:true,
                    }
                }
            />
        </Stack.Navigator>
    );
}

const styles = StyleSheet.create({});

const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(StackNav);
```

`nav-stack-screen`
```
<Stack.Screen
    name="Screen1"
    component={Screen1}
    options={
        {
            title: 'Title',
            headerTitleAlign: 'center', // option (center, left) Defaults to center on iOS and left on Android.
            headerStyle: {},
            headerTitleStyle: {},
            headerBackTitleStyle: {},
            headerLeftContainerStyle: {},
            headerTitleContainerStyle: {},
            headerRightContainerStyle: {},
            headerTintColor: '',
            headerTransparent: false,
            cardShadowEnabled: true,
            cardOverlayEnabled: true, // Defaults to true on Android and false on iOS.
            //headerStatusBarHeight: 0,
            //headerBackground: settings => { return null },
            //header: settings => { return null }, // React Element
            //headerTitle:settings => { return null }, // React Element
            //headerRight: settings => { return null }, // React Element
            //headerLeft: settings => { return null }, // React Element
            //headerBackImage: settings => { return null }, // React element
            //headerBackTitle:'', // Title string used by the back button on iOS. Defaults to the previous scene's headerTitle
            //headerBackTitleVisible:true,
        }
    }
/>
```

`nav-drawer`
```
import { createDrawerNavigator, DrawerContentScrollView, DrawerItemList, DrawerItem } from '@react-navigation/drawer';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const CustomDrawerContent = props => {
    return (
        <DrawerContentScrollView {...props}>
            <DrawerItemList {...props} />
            <DrawerItem
                label="Help"
                onPress={_=> alert('Help Pressed!')}
            />
        </DrawerContentScrollView>
    )
}
const Drawer = createDrawerNavigator();
const AppDrawer = () => {
    return (
        <Drawer.Navigator
            initialRouteName=""
            drawerContent={(props) => <CustomDrawerContent {...props} />}
            screenOptions={}
            openByDefault={false}
            drawerPosition={'left'} // options (left, right)
            drawerType={'front'} // options (front, back, slide, permanent)
            drawerStyle={{}}
            drawerContentOptions={
                {
                    activeTintColor:'black',
                    activeBackgroundColor:'white',
                    inactiveTintColor:'grey',
                    inactiveBackgroundColor:'lightgrey',
                    itemStyle:{},
                    labelStyle:{},
                    contentContainerStyle:{},
                    style:{},
                }
            }
            //sceneContainerStyle={{}}
            hideStatusBar={false}
            statusBarAnimation={'slide'}
            keyboardDismissMode={'on-drag'} // options (on-drag, none)
            backBehavior={'initialRoute'} // options (initialRoute, order, history, none) 
            //edgeWidth={''}
            //minSwipeDistance={''}
            //overlayColor={''}
        >
            <Drawer.Screen
                name="Feed"
                component={Feed}
                options={
                    {
                        title:'Title',
                        swipeEnable: true,
                        gestureEnabled: true,
                        unmountOnBlur: false,
                        drawerLabel: settings => undefined,
                        drawerIcon: settings => undefined, //React Element
                        drawerIcon: settings => undefined, //React Element
                    }
                }
            />
        </Drawer.Navigator>
    )
}
const styles = StyleSheet.create({});
export default AppDrawer;
```

`nav-drawer-redux`
```
import { createDrawerNavigator, DrawerContentScrollView, DrawerItemList, DrawerItem } from '@react-navigation/drawer';
import * as React from 'react'
import {StyleSheet} from 'react-native'
//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const CustomDrawerContent = props => {
    return (
        <DrawerContentScrollView {...props}>
            <DrawerItemList {...props} />
            <DrawerItem
                label="Help"
                onPress={_=> alert('Help Pressed!')}
            />
        </DrawerContentScrollView>
    )
}
const Drawer = createDrawerNavigator();
const AppDrawer = () => {
    return (
        <Drawer.Navigator
            initialRouteName=""
            drawerContent={(props) => <CustomDrawerContent {...props} />}
            screenOptions={}
            openByDefault={false}
            drawerPosition={'left'} // options (left, right)
            drawerType={'front'} // options (front, back, slide, permanent)
            drawerStyle={{}}
            drawerContentOptions={
                {
                    activeTintColor:'black',
                    activeBackgroundColor:'white',
                    inactiveTintColor:'grey',
                    inactiveBackgroundColor:'lightgrey',
                    itemStyle:{},
                    labelStyle:{},
                    contentContainerStyle:{},
                    style:{},
                }
            }
            //sceneContainerStyle={{}}
            hideStatusBar={false}
            statusBarAnimation={'slide'}
            keyboardDismissMode={'on-drag'} // options (on-drag, none)
            backBehavior={'initialRoute'} // options (initialRoute, order, history, none) 
            //edgeWidth={''}
            //minSwipeDistance={''}
            //overlayColor={''}
        >
            <Drawer.Screen
                name="Feed"
                component={Feed}
                options={
                    {
                        title:'Title',
                        swipeEnable: true,
                        gestureEnabled: true,
                        unmountOnBlur: false,
                        drawerLabel: settings => undefined,
                        drawerIcon: settings => undefined, //React Element
                        drawerIcon: settings => undefined, //React Element
                    }
                }
            />
        </Drawer.Navigator>
    )
}
const styles = StyleSheet.create({});

const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(AppDrawer);
```

`nav-drawer-screen`
```
<Drawer.Screen
    name="Feed"
    component={Feed}
    options={
        {
            title:'Title',
            swipeEnable: true,
            gestureEnabled: true,
            unmountOnBlur: false,
            drawerLabel: settings => undefined,
            drawerIcon: settings => undefined, //React Element
            drawerIcon: settings => undefined, //React Element
        }
    }
/>
```

`nav-tab`
```
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const Tab = createBottomTabNavigator();
const Tab = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            //tabBar={_=> null} // REact Element to display tab bar.
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
            tabBarOptions={
                {
                    activeTintColor:'black',
                    activeBackgroundColor:'white',
                    inactiveTintColor:'grey',
                    inactiveBackgroundColor:'lightgrey',
                    showLabel:true,
                    showIcon:true,
                    style:{},
                    labelStyle:{},
                    labelPosition:'beside-icon', // options (below-icon) 
                    keyboardHidesTabBar:false,
                }
            }
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarVisible: true,
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarButton: settings => undefined, // React Element
                        unmountOnBlur: false, 
                    }
                }
            />
        </Tab.Navigator>
    );
}
export default Tab
```

`nav-tab-redux`
```
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const Tab = createBottomTabNavigator();
const Tabs = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            //tabBar={_=> null} // REact Element to display tab bar.
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
            tabBarOptions={
                {
                    activeTintColor:'black',
                    activeBackgroundColor:'white',
                    inactiveTintColor:'grey',
                    inactiveBackgroundColor:'lightgrey',
                    showLabel:true,
                    showIcon:true,
                    style:{},
                    labelStyle:{},
                    labelPosition:'beside-icon', // options (below-icon) 
                    keyboardHidesTabBar:false,
                }
            }
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarVisible: true,
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarButton: settings => undefined, // React Element
                        unmountOnBlur: false, 
                    }
                }
            />
        </Tab.Navigator>
    );
}
const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(Tabs);
```

`nav-tab-screen`
```
<Tab.Screen
    name="Feed"
    component="Feed"
    options={
        {
            title: 'Title',
            tabBarVisible: true,
            tabBarIcon: settings => undefined, // React Element
            tabBarLabel: settings => undefined, // React Element
            tabBarButton: settings => undefined, // React Element
            unmountOnBlur: false, 
        }
    }
/>
```

`nav-tab-m`
```
import { createMaterialBottomTabNavigator } from '@react-navigation/material-bottom-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const Tab = createMaterialBottomTabNavigator();
const MaterialTab = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            shifting={true}
            labeled={true}
            activeColor={'white'}
            inactiveColor={'grey'}
            barStyle={{}}
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarColor: 'blue',
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarBadge: '0'
                    }
                }
            />
        </Tab.Navigator>
    );
}
export default MaterialTab
```

`nav-tab-m-redux`
```
import { createMaterialBottomTabNavigator } from '@react-navigation/material-bottom-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const Tab = createMaterialBottomTabNavigator();

//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const MaterialTab = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            shifting={true}
            labeled={true}
            activeColor={'white'}
            inactiveColor={'grey'}
            barStyle={{}}
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarColor: 'blue',
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarBadge: '0'
                    }
                }
            />
        </Tab.Navigator>
    );
}
const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(MaterialTab);
```

`nav-tab-m-screen`
```
<Tab.Screen
    name="Feed"
    component="Feed"
    options={
        {
            title: 'Title',
            tabBarColor: 'blue',
            tabBarIcon: settings => undefined, // React Element
            tabBarLabel: settings => undefined, // React Element
            tabBarBadge: '0'
        }
    }
/>
```

`nav-tab-top`
```
import { createMaterialTopTabNavigator } from '@react-navigation/material-top-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const Tab = createMaterialTopTabNavigator();
const TopTab = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            style={{}}
            //tabBar={ props => null} //Custom React Element
            swipeEnabled={true}
            tabBarPosition={'top'} // options (bottom) 
            keyboardDismissMode="auto" // options(on-drag, none)
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
            tabBarOptions={
                {
                    activeTintColor:'black',
                    inactiveTintColor:'grey',
                    pressColor:'lightgrey',
                    scrollEnabled: false,
                    showLabel:true,
                    showIcon:true,
                    style:{},
                    labelStyle:{},
                    tabStyle:{},
                    indicatorStyle:{},
                    iconStyle:{},
                    //renderIndicator:{_ => null}, // React Element
                    keyboardHidesTabBar:false,
                }
            }
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarColor: 'blue',
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarBadge: '0'
                    }
                }
            />
        </Tab.Navigator>
    );
}
export default TopTab
```

`nav-tab-top-redux`
```
import { createMaterialTopTabNavigator } from '@react-navigation/material-top-tabs';
import * as React from 'react'
import {StyleSheet} from 'react-native'
const Tab = createMaterialTopTabNavigator();

//redux
import {connect} from 'react-redux';
import { bindActionCreators } from 'redux';

//import actions here
const TopTabs = () => {
    return (
        <Tab.Navigator
            initialRouteName=""
            screenOptions={{}}
            style={{}}
            //tabBar={ props => null} //Custom React Element
            swipeEnabled={true}
            tabBarPosition={'top'} // options (bottom) 
            keyboardDismissMode="auto" // options(on-drag, none)
            backBehavior="initialRoute" // options (initialRoute, order, history, none) 
            tabBarOptions={
                {
                    activeTintColor:'black',
                    inactiveTintColor:'grey',
                    pressColor:'lightgrey',
                    scrollEnabled: false,
                    showLabel:true,
                    showIcon:true,
                    style:{},
                    labelStyle:{},
                    tabStyle:{},
                    indicatorStyle:{},
                    iconStyle:{},
                    //renderIndicator:{_ => null}, // React Element
                    keyboardHidesTabBar:false,
                }
            }
        >
            <Tab.Screen
                name="Feed"
                component="Feed"
                options={
                    {
                        title: 'Title',
                        tabBarColor: 'blue',
                        tabBarIcon: settings => undefined, // React Element
                        tabBarLabel: settings => undefined, // React Element
                        tabBarBadge: '0'
                    }
                }
            />
        </Tab.Navigator>
    );
}
const mapStateToProps = state => {
    return {
        state
    };
};
const mapDispatchToProps = dispatch => 
    bindActionCreators(
        {
            //add actions here
        },
        dispatch,
    );

export default connect(mapStateToProps, mapDispatchToProps)(TopTabs);
```

`nav-tab-top-screen`
```
<Tab.Screen
    name="Feed"
    component="Feed"
    options={
        {
            title: 'Title',
            tabBarColor: 'blue',
            tabBarIcon: settings => undefined, // React Element
            tabBarLabel: settings => undefined, // React Element
            tabBarBadge: '0'
        }
    }
/>
```
## Requirements
Must have this library installed: https://reactnavigation.org

**Enjoy!**
