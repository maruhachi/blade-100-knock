<script setup>
const csvData = `li,series,cast,member,color,code
ll,Aqours,伊波杏樹,高海千歌,みかん色,#FF9547
ll,Aqours,逢田梨香子,桜内梨子,サクラピンク,#FF9EAC
ll,Aqours,諏訪ななか,松浦果南,エメラルドグリーン,#27C1B7
ll,Aqours,小宮有紗,黒澤ダイヤ,レッド,#DB0839
ll,Aqours,斉藤朱夏,渡辺 曜,ライトブルー,#66C0FF
ll,Aqours,小林愛香,津島善子,ホワイト,#C1CAD4
ll,Aqours,高槻かなこ,国木田花丸,イエロー,#FFD010
ll,Aqours,鈴木愛奈,小原鞠莉,バイオレット,#C252C6
ll,Aqours,降幡 愛,黒澤ルビィ,ピンク,#FF6FBE
ll,虹ヶ咲学園スクールアイドル同好会,大西亜玖璃,上原歩夢,ライトピンク,#ED7D95
ll,虹ヶ咲学園スクールアイドル同好会,相良茉優,中須かすみ,パステルイエロー,#E7D600
ll,虹ヶ咲学園スクールアイドル同好会,前田佳織里,桜坂しずく,ライトブルー,#01B7ED
ll,虹ヶ咲学園スクールアイドル同好会,久保田未夢,朝香果林,ロイヤルブルー,#485EC6
ll,虹ヶ咲学園スクールアイドル同好会,村上奈津実,宮下 愛,超オレンジ,#FF5800
ll,虹ヶ咲学園スクールアイドル同好会,鬼頭明里,近江彼方,すみれ色,#A664A0
ll,虹ヶ咲学園スクールアイドル同好会,林 鼓子,優木せつ菜,スカーレット,#D81C2F
ll,虹ヶ咲学園スクールアイドル同好会,指出毬亜,エマ・ヴェルデ,ライトグリーン,#84C36E
ll,虹ヶ咲学園スクールアイドル同好会,田中ちえ美,天王寺璃奈,ペーパーホワイト,#9CA5B9
ll,虹ヶ咲学園スクールアイドル同好会,小泉萌香,三船栞子,翡翠,#37B484
ll,虹ヶ咲学園スクールアイドル同好会,内田 秀,ミア・テイラー,プラチナシルバー,#A99E98
ll,虹ヶ咲学園スクールアイドル同好会,法元明菜,鐘 嵐珠,ピンクゴールド,#F8C8C4
ll,Liella!,伊達さゆり,澁谷かのん,マリーゴールド,#FF7F27
ll,Liella!,Liyuu,唐 可可,パステルブルー,#A0FFF9
ll,Liella!,岬 なこ,嵐 千砂都,ピーチピンク,#FF6E90
ll,Liella!,ペイトン尚未,平安名すみれ,メロングリーン,#74F466
ll,Liella!,青山なぎさ,葉月 恋,サファイアブルー,#0000A0
ll,Liella!,鈴原希実,桜小路きな子,メイズイエロー,#FFF442
ll,Liella!,薮島朱音,米女メイ,ルージュ,#FF3535
ll,Liella!,大熊和奏,若菜四季,アイスグリーンホワイト,#B2FFDD
ll,Liella!,絵森 彩,鬼塚夏美,オニナッツピンク,#FF51C4
ll,Liella!,結那,ウィーン・マルガレーテ,エレガントパープル,#E49DFD
ll,Liella!,坂倉 花,鬼塚冬毬,スモーキーブルー,#76DDDF
ll,蓮ノ空女学院スクールアイドルクラブ,楡井希実,日野下花帆,おひさま色,#F8B500
ll,蓮ノ空女学院スクールアイドルクラブ,野中ここな,村野さやか,氷青色,#5383C3
ll,蓮ノ空女学院スクールアイドルクラブ,花宮初奈,乙宗 梢,マーメイドグリーン,#68BE8D
ll,蓮ノ空女学院スクールアイドルクラブ,佐々木琴子,夕霧綴理,ボクの赤,#BA2636
ll,蓮ノ空女学院スクールアイドルクラブ,菅 叶和,大沢瑠璃乃,瑠璃ピンク,#E7609E
ll,蓮ノ空女学院スクールアイドルクラブ,月音こな,藤島 慈,エンジェルホワイト,#C8C2C6`;

import { ref } from "vue";

const lineList = csvData.split("\n");
// 1行目はKeyとして利用するため
const keyList = lineList[0].split(",");
const dataList = lineList
  .filter((_, index) => index !== 0) // 2行目以降がデータのため
  .map((line) => {
    const valueList = line.split(",");
    const tmpObj = {};
    keyList.map((key, index) => (tmpObj[key] = valueList[index]));
    return tmpObj;
  });

const target = ref(0);
const score = ref(0);
const total = ref(dataList.length);

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
  if (target.value == dataList.length - 1) {
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

function answer(answerNum) {
  if (
    choices.value[answerNum]["member"] ==
    questionList.value[target.value]["member"]
  ) {
    score.value++;
  }
  result.value =
    "正解: " +
    questionList.value[target.value]["member"] +
    ", 回答 : " +
    choices.value[answerNum]["member"] +
    "\r\n" +
    result.value;
  next();
}

const tmpResult = "";
const result = ref("");

function finish() {
  alert("終了！ " + score.value + " / 38問 正解");
  result.value = tmpResult;
}

const memberCheck = ref(false);
function memberHint(e) {
  if (this.memberCheck) {
    document
      .querySelectorAll(".member")
      .forEach((i) => i.classList.add("invisible"));
  } else {
    document
      .querySelectorAll(".member")
      .forEach((i) => i.classList.remove("invisible"));
  }
}

const colorNameCheck = ref(false);

function colorHint(e) {
  if (this.colorNameCheck) {
    document
      .querySelectorAll(".color-name")
      .forEach((i) => i.classList.add("invisible"));
  } else {
    document
      .querySelectorAll(".color-name")
      .forEach((i) => i.classList.remove("invisible"));
  }
}
</script>

<template>
  <main>
    <div class="info">
      <div class="series">シリーズ名：{{ questionList[target]["series"] }}</div>
      <div class="member">メンバー名：{{ questionList[target]["member"] }}</div>
      <div class="cast">キャスト名：{{ questionList[target]["cast"] }}</div>
      <div class="colors">
        <button
          class="color"
          :style="{ backgroundColor: choices[0]['code'] }"
          @click="answer(0)"
        >
          <span class="color-name">{{ choices[0]["color"] }}</span>
        </button>
        <button
          class="color"
          :style="{ backgroundColor: choices[1]['code'] }"
          @click="answer(1)"
        >
          <span class="color-name">{{ choices[1]["color"] }}</span>
        </button>
        <button
          class="color"
          :style="{ backgroundColor: choices[2]['code'] }"
          @click="answer(2)"
        >
          <span class="color-name">{{ choices[2]["color"] }}</span>
        </button>
        <button
          class="color"
          :style="{ backgroundColor: choices[3]['code'] }"
          @click="answer(3)"
        >
          <span class="color-name">{{ choices[3]["color"] }}</span>
        </button>
      </div>
    </div>
    <div class="control">
      <a class="ctrlbtn next" @click="next">
        <span>分からん！</span>
      </a>
      <div class="score">
        <p>スコア : {{ score }} / {{ total }} 正解</p>
      </div>
      <p>ヒント設定</p>
      <div block-hint>
        <div class="hints">
          <label for="chMember">メンバー名を表示</label>
          <input
            id="chMember"
            type="checkbox"
            class="ctrlbtn hint1"
            v-model="memberCheck"
            @change="memberHint($event)"
          />
        </div>
        <div class="hints">
          <label for="chColor">色名を表示</label>
          <input
            id="chColor"
            type="checkbox"
            class="ctrlbtn hint2"
            v-model="colorNameCheck"
            @change="colorHint($event)"
          />
        </div>
      </div>
      <h3>リザルト</h3>
      <div class="block-result">
        <p class="result-text">{{ result }}</p>
      </div>
    </div>
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

.control {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.hints {
  display: flex;
  width: 70vw;
  justify-content: space-between;
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
  width: 30vw;
  height: 4vh;
  border: 1px solid black;
}

.invisible {
  display: none;
}

.block-result {
  padding: 0 10px;
}
.result-text {
  white-space: pre-wrap;
}

header .wrapper {
  display: flex;
  place-items: flex-start;
  flex-wrap: wrap;
}
</style>
