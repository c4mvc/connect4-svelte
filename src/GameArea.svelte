<script>
  const playerType = {
    One: 1,
    Two: 2,
    None: 0
  };

  const totalRows = 6;
  const totalColumns = 7;

  const gameCursorNumber = new Array(totalColumns);

  const gameCursor = [];

  function GameCursor(isAvailable, columnIndex, player) {
    this.isAvailable = isAvailable;
    this.columnIndex = columnIndex;
    this.player = player;
  }

  const loadGameCursor = columnIndex => {
    for (let index = 0; index < totalColumns; index++) {
      let cursorObj = new GameCursor(false, index, playerType.None);
      gameCursor.push(cursorObj);
    }
    gameCursor[columnIndex] = new GameCursor(
      false,
      columnIndex,
      playerType.One
    );

    console.log("gameCursor", gameCursor);
  };

  loadGameCursor(0);
</script>

<style>
  .CircleBase {
    border-radius: 50%;
  }

  .CircleRed {
    width: 50px;
    height: 50px;
    background: red;
    border: 3px solid red;
    margin: auto;
  }

  .CircleYellow {
    width: 50px;
    height: 50px;
    background: yellow;
    border: 3px solid yellow;
    margin: auto;
  }

  .CursorArea {
    width: 70px;
    height: 70px;
    padding-top: 45px;
    border: none;
    float: left;
  }
</style>

<div class="row">
  <div class="row">
    <div class="col-xs-9">

      <div class="bottom-buffer">
        <div class="clearfix area-width">
          {#each gameCursor as cursor, index}
            <!-- <li>{cursor}</li> -->
            <div class="CursorArea">
              <div style="vertical-align: middle">
                {#if cursor.player === playerType.One}
                  <div class="CircleBase CircleRed"></div>
                {/if}
                {#if cursor.player === playerType.Two}
                  <div class="CircleBase CircleYellow"></div>
                {/if}
              </div>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</div>
