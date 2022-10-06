# array-of-objects-in-a-tabular-form
Class a Class Component for viewing an array of objects in a tabular form
function MyTable() {
  const initState = [
    { id: 1, name: "bread", quantitiy: 50, location: "cupboard" },
    { id: 2, name: "milk", quantitiy: 20, location: "fridge" },
    { id: 3, name: "water", quantitiy: 10, location: "fridge" }
  ];
  const [state, setState] = React.useState(initState);

  return (
    <table>
      <tr key={"header"}>
        {Object.keys(state[0]).map((key) => (
          <th>{key}</th>
        ))}
      </tr>
      {state.map((item) => (
        <tr key={item.id}>
          {Object.values(item).map((val) => (
            <td>{val}</td>
          ))}
        </tr>
      ))}
    </table>
  );
}

ReactDOM.render(<MyTable />, document.getElementById("target"));
th,
td {
  border: 1px solid black;
  margin: 0px 0px;
  padding: 5px 5px;
}
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/16.13.1/umd/react.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/16.13.1/umd/react-dom.production.min.js"></script>
<div id="target"></div>
