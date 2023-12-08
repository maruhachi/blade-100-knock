<script setup>
const csvData = `li,series,cast,member,code,day
ll,Aqours,伊波杏樹,高海千歌,#FF9547,両日
ll,Aqours,逢田梨香子,桜内梨子,#FF9EAC,両日
ll,Aqours,諏訪ななか,松浦果南,#27C1B7,両日
ll,Aqours,小宮有紗,黒澤ダイヤ,#DB0839,両日
ll,Aqours,斉藤朱夏,渡辺 曜,#66C0FF,両日
ll,Aqours,小林愛香,津島善子,#C1CAD4,両日
ll,Aqours,高槻かなこ,国木田花丸,#FFD010,両日
ll,Aqours,鈴木愛奈,小原鞠莉,#C252C6,両日
ll,Aqours,降幡 愛,黒澤ルビィ,#FF6FBE,両日
ll,虹ヶ咲学園スクールアイドル同好会,大西亜玖璃,上原歩夢,#ED7D95,両日
ll,虹ヶ咲学園スクールアイドル同好会,相良茉優,中須かすみ,#E7D600,両日
ll,虹ヶ咲学園スクールアイドル同好会,前田佳織里,桜坂しずく,#01B7ED,両日
ll,虹ヶ咲学園スクールアイドル同好会,久保田未夢,朝香果林,#485EC6,両日
ll,虹ヶ咲学園スクールアイドル同好会,村上奈津実,宮下 愛,#FF5800,両日
ll,虹ヶ咲学園スクールアイドル同好会,鬼頭明里,近江彼方,#A664A0,両日
ll,虹ヶ咲学園スクールアイドル同好会,林 鼓子,優木せつ菜,#D81C2F,両日
ll,虹ヶ咲学園スクールアイドル同好会,指出毬亜,エマ・ヴェルデ,#84C36E,両日
ll,虹ヶ咲学園スクールアイドル同好会,田中ちえ美,天王寺璃奈,#9CA5B9,両日
ll,虹ヶ咲学園スクールアイドル同好会,小泉萌香,三船栞子,#37B484,両日
ll,虹ヶ咲学園スクールアイドル同好会,内田 秀,ミア・テイラー,#A99E98,両日
ll,虹ヶ咲学園スクールアイドル同好会,法元明菜,鐘 嵐珠,#F8C8C4,両日
ll,Liella!,伊達さゆり,澁谷かのん,#FF7F27,両日
ll,Liella!,Liyuu,唐 可可,#A0FFF9,両日
ll,Liella!,岬 なこ,嵐 千砂都,#FF6E90,両日
ll,Liella!,ペイトン尚未,平安名すみれ,#74F466,両日
ll,Liella!,青山なぎさ,葉月 恋,#0000A0,両日
ll,Liella!,鈴原希実,桜小路きな子,#FFF442,両日
ll,Liella!,薮島朱音,米女メイ,#FF3535,両日
ll,Liella!,大熊和奏,若菜四季,#B2FFDD,両日
ll,Liella!,絵森 彩,鬼塚夏美,#FF51C4,両日
ll,Liella!,結那,ウィーン・マルガレーテ,#E49DFD,両日
ll,Liella!,坂倉 花,鬼塚冬毬,#76DDDF,両日
ll,蓮ノ空女学院スクールアイドルクラブ,楡井希実,日野下花帆,#F8B500,両日
ll,蓮ノ空女学院スクールアイドルクラブ,野中ここな,村野さやか,#5383C3,両日
ll,蓮ノ空女学院スクールアイドルクラブ,花宮初奈,乙宗 梢,#68BE8D,両日
ll,蓮ノ空女学院スクールアイドルクラブ,佐々木琴子,夕霧綴理,#BA2636,両日
ll,蓮ノ空女学院スクールアイドルクラブ,菅 叶和,大沢瑠璃乃,#E7609E,両日
ll,蓮ノ空女学院スクールアイドルクラブ,月音こな,藤島 慈,#C8C2C6,両日
imas,シンデレラガールズ,藍原ことみ,一ノ瀬志希,#a50050,day1
imas,シンデレラガールズ,五十嵐裕美,双葉 杏,#f8a3bc,day1
imas,シンデレラガールズ,髙野麻美,宮本フレデリカ,#a20067,day1
imas,シンデレラガールズ,中島由貴,乙倉悠貴,#e3bec3,day1
imas,シンデレラガールズ,飯田友子,速水 奏,#033087,day1
imas,シンデレラガールズ,井上ほの花,浅利七海,#009cbcday1
imas,シンデレラガールズ,上坂すみれ,アナスタシア,#b1c9e8,day1
imas,シンデレラガールズ,洲崎 綾,新田美波,#71c5e8,day1
imas,シンデレラガールズ,富田美憂,砂塚あきら,#7e93a7,day1
imas,シンデレラガールズ,ルゥティン,塩見周子,#dce6ed,day1
imas,シンデレラガールズ,生田 輝,ナターリア,#f5633a,day1
imas,シンデレラガールズ,立花日菜,久川 凪,#f8a3bc,day1
imas,シンデレラガールズ,山下七海,大槻 唯,#f6be00,day1
imas,シンデレラガールズ,大橋彩香,島村卯月,#f67499,day2
imas,シンデレラガールズ,福原綾香,渋谷 凛,#0f9dde,day2
imas,シンデレラガールズ,原 紗友里,本田未央,#feb81c,day2
imas,シンデレラガールズ,佐藤亜美菜,橘 ありす,#5c88da,day2
imas,シンデレラガールズ,黒沢ともよ,赤城みりあ,#ffcd00,day2
imas,シンデレラガールズ,集貝はな,的場梨沙,#e01a95,day2
imas,シンデレラガールズ,小市眞琴,結城 晴,#71dad4,day2
imas,シンデレラガールズ,今井麻夏,佐々木千枝,#0072ce,day2
imas,シンデレラガールズ,春瀬なつみ,龍崎 薫,#fae053,day2
imas,シンデレラガールズ,久野美咲,市原仁奈,#f7de8c,day2
imas,ミリオンライブ！,山崎はるか,春日未来,#ea5b76,day1
imas,ミリオンライブ！,田所あずさ,最上静香,#6495cf,day1
imas,ミリオンライブ！,Machico,伊吹 翼,#fed552,day1
imas,ミリオンライブ！,麻倉もも,箱崎星梨花,#ed90ba,day1
imas,ミリオンライブ！,小岩井ことり,天空橋朋花,#bee3e3,day1
imas,ミリオンライブ！,中村温姫,ロコ,#fff03c,day1
imas,ミリオンライブ！,平山笑美,北上麗花,#6bb6b0,day1
imas,ミリオンライブ！,渡部優衣,横山奈緒,#788bc5,day1
imas,ミリオンライブ！,愛美,ジュリア,#d7385f,day2
imas,ミリオンライブ！,伊藤美来,七尾百合子,#c7b83c,day2
imas,ミリオンライブ！,木戸衣吹,矢吹可奈,#f5ad3b,day2
imas,ミリオンライブ！,香里有佐,桜守歌織,#274079,day2
imas,ミリオンライブ！,駒形友梨,高山紗代子,#7f6575,day2
imas,ミリオンライブ！,末柄里恵,豊川風花,#7278a8,day2
imas,ミリオンライブ！,南 早紀,白石 紬,#ebe1ff,day2
imas,ミリオンライブ！,山口立花子,百瀬莉緒,#f19591,day2
imas,シャイニーカラーズ,礒部花凜,月岡恋鐘,#f84cad,day1
imas,シャイニーカラーズ,菅沼千紗,田中摩美々,#a846fb,day1
imas,シャイニーカラーズ,八巻アンナ,白瀬咲耶,#006047,day1
imas,シャイニーカラーズ,希水しお,三峰結華,#3b91c4,day1
imas,シャイニーカラーズ,結名美月,幽谷霧子,#d9f2ff,day1
imas,シャイニーカラーズ,黒木ほの香,大崎甘奈,#f54275,day1
imas,シャイニーカラーズ,前川涼子,大崎甜花,#e75bec,day1
imas,シャイニーカラーズ,芝崎典子,桑山千雪,#fafafa,day1
imas,シャイニーカラーズ,和久井 優,浅倉 透,#50d0d0,day1
imas,シャイニーカラーズ,土屋李央,樋口円香,#be1e3e,day1
imas,シャイニーカラーズ,田嶌紗蘭,福丸小糸,#7967c3,day1
imas,シャイニーカラーズ,岡咲美保,市川雛菜,#ffc639,day1
imas,シャイニーカラーズ,紫月杏朱彩,七草にちか,#a6cdb6,day1
imas,シャイニーカラーズ,山根 綺,緋田美琴,#760f10,day1
imas,シャイニーカラーズ,関根 瞳,櫻木真乃,#ffbad6,day2
imas,シャイニーカラーズ,近藤玲奈,風野灯織,#144384,day2
imas,シャイニーカラーズ,峯田茉優,八宮めぐる,#ffe012,day2
imas,シャイニーカラーズ,河野ひより,小宮果穂,#e5461c,day2
imas,シャイニーカラーズ,白石晴香,園田智代子,#f93b90,day2
imas,シャイニーカラーズ,永井真里子,西城樹里,#ffc602,day2
imas,シャイニーカラーズ,丸岡和佳奈,杜野凛世,#89c3eb,day2
imas,シャイニーカラーズ,涼本あきほ,有栖川夏葉,#90e667,day2
imas,シャイニーカラーズ,田中有紀,芹沢あさひ,#f30100,day2
imas,シャイニーカラーズ,幸村恵理,黛 冬優子,#5aff19,day2
imas,シャイニーカラーズ,北原沙弥香,和泉愛依,#ff00ff,day2
imas,シャイニーカラーズ,川口莉奈,斑鳩ルカ,#23120c,day2
imas,シャイニーカラーズ,三川華月,鈴木羽那,#e4cad5,day2
imas,シャイニーカラーズ,小澤麗那,郁田はるき,#f8e5b2,day2`;

import { ref } from "vue";
const mode = new URL(window.location.href).searchParams.get("mode");

const lineList = csvData.split("\n");
// 1行目はKeyとして利用するため
const keyList = lineList[0].split(",");
const dataList = lineList
  .filter((_, index) => index !== 0) // 2行目以降がデータのため
  .filter((i) => {
    if (mode == "imas") {
      return i.startsWith("imas");
    } else if (mode == "ll") {
      return i.startsWith("ll");
    } else {
      return true;
    }
  })
  .map((line) => {
    const valueList = line.split(",");
    const tmpObj = {};
    keyList.map((key, index) => (tmpObj[key] = valueList[index]));
    return tmpObj;
  });

const target = ref(0);
const score = ref(0);
const total = ref(dataList.length > 50 ? 50 : dataList.length);

const questionList = ref([...dataList.sort(() => Math.random() - 0.5)]);
const addChoice = ref(
  questionList.value
    .filter((n) => n !== questionList.value[0])
    .sort(() => Math.random() - 0.5)
);

const choices = ref([
  questionList.value[0],
  addChoice.value[1],
  addChoice.value[2],
  addChoice.value[3],
]);

function next() {
  if (target.value == 49) {
    finish();
    return;
  }
  target.value++;
  const candidate = questionList.value
    .filter((n) => n["member"] !== questionList.value[target.value]["member"])
    .sort(() => Math.random() - 0.5)
    .slice(0, 3);
  choices.value = [
    questionList.value[target.value],
    candidate[0],
    candidate[1],
    candidate[2],
  ].sort(() => Math.random() - 0.5);
}

const resultList = ref([]);
const resultText = ref("");

function answer(answerNum) {
  const isCollect =
    choices.value[answerNum]["member"] ==
    questionList.value[target.value]["member"];
  if (isCollect) {
    score.value++;
  }
  resultList.value.unshift({
    resultText:
      (isCollect ? "○ : " : "✕ : ") +
      questionList.value[target.value]["member"] +
      ", 回答 : " +
      choices.value[answerNum]["member"],
    color: questionList.value[target.value]["code"],
    textColor: isCollect ? "black" : "red",
  });
  next();
}

function finish() {
  resultText.value = "終了！ " + score.value + " / " + total.value + "問 正解";
  document.querySelector("dialog").showModal();
  document.querySelector("dialog").classList.remove("is-close");
}

const memberCheck = ref(false);
function memberHint(e) {
  if (memberCheck.value) {
    document
      .querySelectorAll(".member")
      .forEach((i) => i.classList.add("invisible"));
  } else {
    document
      .querySelectorAll(".member")
      .forEach((i) => i.classList.remove("invisible"));
  }
}

function retry() {
  document.querySelector("dialog").classList.add("is-close");
  document.querySelector("dialog").close();
  location.reload();
}
</script>

<template>
  <main>
    <div class="info">
      <div class="series">シリーズ名：{{ questionList[target]["series"] }}</div>
      <div class="member">メンバー名：{{ questionList[target]["member"] }}</div>
      <div class="cast">キャスト名：{{ questionList[target]["cast"] }}</div>
      <div class="cast">出演：{{ questionList[target]["day"] }}</div>
      <div class="colors">
        <button
          class="color"
          :style="{ backgroundColor: choices[0]['code'] }"
          @click="answer(0)"
        ></button>
        <button
          class="color"
          :style="{ backgroundColor: choices[1]['code'] }"
          @click="answer(1)"
        ></button>
        <button
          class="color"
          :style="{ backgroundColor: choices[2]['code'] }"
          @click="answer(2)"
        ></button>
        <button
          class="color"
          :style="{ backgroundColor: choices[3]['code'] }"
          @click="answer(3)"
        ></button>
      </div>
    </div>
    <div class="control">
      <a class="ctrlbtn next" @click="next"> 分からん！</a>
      <div class="score">
        <p>
          スコア : <span class="score-text">{{ score }}</span> /
          {{ total }} 正解 <span class="qNo">(現在 {{ target + 1 }}問目)</span>
        </p>
      </div>
      <div class="block-mode">
        <p>モード設定</p>
        <a class="mode" href="/index.html">全アイドル</a>
        <a class="mode" href="/index.html?mode=imas">アイマスオンリー</a>
        <a class="mode" href="/index.html?mode=ll">ラブライブ！オンリー</a>
      </div>
      <div class="block-hint">
        <p>ヒント設定</p>
        <div class="hints">
          <label for="chMember">メンバー名を非表示</label>
          <input
            id="chMember"
            type="checkbox"
            class="ctrlbtn hint1"
            v-model="memberCheck"
            @change="memberHint($event)"
          />
        </div>
      </div>
      <h3>リザルト</h3>
      <div class="block-result">
        <div class="result" v-for="item in resultList">
          <i class="collect-color" :style="{ backgroundColor: item.color }"></i>
          <p class="result-text" :style="{ color: item.textColor }">
            {{ item.resultText }}
          </p>
        </div>
      </div>
    </div>
    <dialog class="is-close">
      <p>{{ resultText }}</p>
      <button id="retry" @click="retry">もう一回！</button>
    </dialog>
  </main>
</template>

<style scoped lang="scss">
main {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.info > div {
  padding: 2px 0px;
}
.score-text {
  font-size: larger;
}
.qNo {
  font-size: small;
  color: rgb(49, 49, 49);
}
.control {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.block-mode > p {
  padding: 3px 0;
}
a.mode {
  display: block;
}
.hints {
  display: flex;
  width: 70vw;
  padding: 5px;
}
.colors {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.color {
  width: 23vw;
  height: 20vh;
  text-align: center;
  vertical-align: middle;
}

.ctrlbtn {
  display: block;
  width: 10;
  height: auto;
  border: 1px solid black;
}

.invisible {
  display: none;
}

.block-result {
  padding: 0 10px;
}

.result {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.result-text {
  padding-left: 3px;
}

.collect-color {
  height: 18px;
  width: 28px;
  border: 0.5px solid rgb(167, 166, 166);
}

header .wrapper {
  display: flex;
  place-items: flex-start;
  flex-wrap: wrap;
}

dialog {
  // 画面中央寄せ
  position: absolute;
  left: 50%;
  top: 30%;
  transform: translate(-50%, -50%);

  width: 70vw;
  height: 30vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
  font-size: larger;
}

dialog.is-close {
  display: none;
}
</style>
