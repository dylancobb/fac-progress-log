## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/client-side-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
> **Use component state to manage DOM updates**  
> Our app was structured roughly:
```js
<App>
  <Stuff />
  <Board>
    <Cell /> // the board contains many of these Cell components
  </Board>
</App>
```
After an initial attempt to manage the state of each Cell individually at the Cell level, it became apparent that this made it impossible to communicate between sibling components. Eventually I lifted up state to the App level, as a 2-dimensional array of objects, and instead passed the getter/setter for this top-level state object as props to each Cell:
```js
// creation of the data object
const createBoard = (rows, cols, mines) => {
    const data = createEmptyArray(rows, cols);
    plantMines(data, mines);
    countNeighbours(data);

    return data;
}

const createEmptyArray = (rows, cols) => {
    let data = [];

    for (let i = 0; i < rows; i++) {
        data.push([]);
        for (let j = 0; j < cols; j++) {
            data[i][j] = {
                x: i,
                y: j,
                isMine: false,
                neighbours: 0,
                state: "",
            };
        }
    }
    //   console.log(data);
    return data;
}
```
In `App.jsx`:
```js
const [data, setData] = useState(createBoard(rows, cols, mines))
...
<Board
  data={data}
  setData={setData}
  lowerCounter={lowerCounter}
  setGameState={setGameState}
  gameCount={gameCount}
/>
```
When any cell needs to change the state, the data object can be indexed into, changes made, and then applied via setData. This also allows sibling components to affect each other's display.

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> **Manage side effects in our components** 
> I didn't get an opportunity to use the useEffect hook, nor any custom hooks, this week. I'd definitely like to re-visit these and make sure I'm confident I understand their usage.

## Feedback
### Alphonso's feedback
#### What Went Well
This is a great example of a raised state! The shift in thinking that you highlighted here is exactly the main challenge when you move onto working with React.

#### Even Better If
There's quite a bit of material out there about the different hooks available but if you want to look at an example applied to the codebase of another group in the cohort there is this [review of PetProgrammer](https://github.com/fac28/PetProgrammer/issues/27) I submitted that talks a bit about a case in their code that *could* have been addressed with a `useEffect`
