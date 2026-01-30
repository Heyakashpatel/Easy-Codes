```Html
<details class="info-card">
      <summary>
        Info
      </summary>
      <p>vbvfjnfjencfewncjewncjnewjcnejcnjencjencjnvnfvnevn</p>
 </details>
 ```

 ```Css
 /*Details Styles*/
.info-card summary{
  background: tomato;
  padding: 15px;
  max-width: fit-content;
  border-radius: 6px;
  cursor: pointer;
  font-size: 20px;
}

.info-card p{
  background: tomato;
  padding: 15px;
  border-radius: 6px;
  max-width: fit-content;
  cursor: pointer;
  font-size: 20px;
  margin-top: 5px;
}

/*This Changes Icons On Click Using Marker*/
.info-card summary::marker{
  content: "➤";
}

/*For Icon To Change On Click Add [open] To Details Or With The Class On Details*/
.info-card[open] summary::marker {
  content: "▼";
}

/*This will Prevent Copy/Highlight when clicked on Button*/
.info-card ::selection {
  background: transparent;
}
```
