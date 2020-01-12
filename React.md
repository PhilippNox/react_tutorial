Source: https://ru.reactjs.org/tutorial/tutorial.html#adding-time-travel

### How to init react app
npx create-react-app my-app
cd my-app

### How to run react app
npm start
http://localhost:3000

### Компонент React: Подклассов (Подскасс | Функциональный)
## Пример: class ShoppingList extends React.Component
  👉Наследуется от React.Component.
  👉Имеет метод render() {} c JSX описпнием внутри.
  👉Имеет props передаваемые при создании, доступные по this.props.xxx
  👉Имеет state внутринее состояние компонента, доступно по this.state
  👑Функции внутри класс могут исползовать prop и state !
      renderSquare(i) {
        return <Square value={this.state.squares[i]} />;
      }
  👑Дочерним компонентам можно передать функции данного класс как props
      renderSquare(i) {
        return (
          <Square
            value={this.state.squares[i]}
            onClick={() => this.handleClick(i)} /> ); }

### Что такое JSX
  👉Это html теги         | <div>, <li>, <h1>, ...
  👉Это js в скобках      | <h1>Имя: {this.props.name}</h1>
  👉Это react компоненты  | <ShoppingList name={"Bob"} />;  

### Что такое state или как его использовать
  👉Добавить констурктор в класс
        constructor(props)
        {
          super(props);   //должны начинаться с вызова super(props)
          this.state = {
            value: null,
          };
        }
  👉Получить значение | this.state.value
  👉Обновить значение | this.setState({value: 'X'})
        Этот метод также обновить компоненту и его дочернии компоненты


### Компонент React: Функциональным компонент.
  👉Просто функция.
  👉Имеет метод render() {} c JSX описпнием внутри.
  👉Имеет props передаваемые при вызове, доступные по props.xxx
## Пример:
    function Square(props) {
      return (
        <button className="square" onClick={props.onClick}>
          {props.value}
        </button>
      );
    }
