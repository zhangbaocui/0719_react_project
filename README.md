## React 项目每天任务表

### day01 任务：

- 1.使用 create-react-app 创建基于 react 脚手架应用（最好精简一下脚手架）
- 2.引入 antd，完成按需引入，自定义主题
- 3.login 静态页面（不使用 atnd 的任何组件）
- 4.login 的 Form 表单（不加校验，只是使用静态的 Form）
- 5.login 的 Form 表单（给用户名加校验，声明式验证）
- 6.login 的 Form 表单（给密码加校验，自定义验证）
- 7.理解好 Form.create()(Login)
- 8.高阶组件、高阶函数

  1. 高阶函数
     定义: 如果函数接收的参数是函数或者返回值是函数
     例子: Promise() / then() / 定时器 / 数组遍历相关方法 / bind() / $() / $.get() / Form.create()
     好处: 更加动态, 更加具有扩展性

  2. 高阶组件
     定义: 参数为组件，返回值为新组件的函数
     例子: Form.create()(组件) / withRouter(组件) / connect()(组件)
     与高阶函数的关系?  
      高阶组件是一个特别的高阶函数
     接收的是组件函数, 同时返回新的组件函数
     作用:
     React 中用于复用组件逻辑的一种高级技巧

     Form.create()(Login), 接收一个 Form 组件, 返回一个新组件
     Form.create = function () {
     const form = 创建一个强大 form 对象
     return function (FormComponent) {
     return class WrapComponent extends Component {
     render () {
     return <Login form={form}/>
     }
     }
     }
     }
     const LoginWrap = Form.create()(Login)
