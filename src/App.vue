<script setup>
const csvData = `li,series,cast,member,color,code,day
ll,Aqours,伊波杏樹,高海千歌,みかん色,#FF9547,両日
ll,Aqours,逢田梨香子,桜内梨子,サクラピンク,#FF9EAC,両日
ll,Aqours,諏訪ななか,松浦果南,エメラルドグリーン,#27C1B7,両日
ll,Aqours,小宮有紗,黒澤ダイヤ,レッド,#DB0839,両日
ll,Aqours,斉藤朱夏,渡辺 曜,ライトブルー,#66C0FF,両日
ll,Aqours,小林愛香,津島善子,ホワイト,#C1CAD4,両日
ll,Aqours,高槻かなこ,国木田花丸,イエロー,#FFD010,両日
ll,Aqours,鈴木愛奈,小原鞠莉,バイオレット,#C252C6,両日
ll,Aqours,降幡 愛,黒澤ルビィ,ピンク,#FF6FBE,両日
ll,虹ヶ咲学園スクールアイドル同好会,大西亜玖璃,上原歩夢,ライトピンク,#ED7D95,両日
ll,虹ヶ咲学園スクールアイドル同好会,相良茉優,中須かすみ,パステルイエロー,#E7D600,両日
ll,虹ヶ咲学園スクールアイドル同好会,前田佳織里,桜坂しずく,ライトブルー,#01B7ED,両日
ll,虹ヶ咲学園スクールアイドル同好会,久保田未夢,朝香果林,ロイヤルブルー,#485EC6,両日
ll,虹ヶ咲学園スクールアイドル同好会,村上奈津実,宮下 愛,超オレンジ,#FF5800,両日
ll,虹ヶ咲学園スクールアイドル同好会,鬼頭明里,近江彼方,すみれ色,#A664A0,両日
ll,虹ヶ咲学園スクールアイドル同好会,林 鼓子,優木せつ菜,スカーレット,#D81C2F,両日
ll,虹ヶ咲学園スクールアイドル同好会,指出毬亜,エマ・ヴェルデ,ライトグリーン,#84C36E,両日
ll,虹ヶ咲学園スクールアイドル同好会,田中ちえ美,天王寺璃奈,ペーパーホワイト,#9CA5B9,両日
ll,虹ヶ咲学園スクールアイドル同好会,小泉萌香,三船栞子,翡翠,#37B484,両日
ll,虹ヶ咲学園スクールアイドル同好会,内田 秀,ミア・テイラー,プラチナシルバー,#A99E98,両日
ll,虹ヶ咲学園スクールアイドル同好会,法元明菜,鐘 嵐珠,ピンクゴールド,#F8C8C4,両日
ll,Liella!,伊達さゆり,澁谷かのん,マリーゴールド,#FF7F27,両日
ll,Liella!,Liyuu,唐 可可,パステルブルー,#A0FFF9,両日
ll,Liella!,岬 なこ,嵐 千砂都,ピーチピンク,#FF6E90,両日
ll,Liella!,ペイトン尚未,平安名すみれ,メロングリーン,#74F466,両日
ll,Liella!,青山なぎさ,葉月 恋,サファイアブルー,#0000A0,両日
ll,Liella!,鈴原希実,桜小路きな子,メイズイエロー,#FFF442,両日
ll,Liella!,薮島朱音,米女メイ,ルージュ,#FF3535,両日
ll,Liella!,大熊和奏,若菜四季,アイスグリーンホワイト,#B2FFDD,両日
ll,Liella!,絵森 彩,鬼塚夏美,オニナッツピンク,#FF51C4,両日
ll,Liella!,結那,ウィーン・マルガレーテ,エレガントパープル,#E49DFD,両日
ll,Liella!,坂倉 花,鬼塚冬毬,スモーキーブルー,#76DDDF,両日
ll,蓮ノ空女学院スクールアイドルクラブ,楡井希実,日野下花帆,おひさま色,#F8B500,両日
ll,蓮ノ空女学院スクールアイドルクラブ,野中ここな,村野さやか,氷青色,#5383C3,両日
ll,蓮ノ空女学院スクールアイドルクラブ,花宮初奈,乙宗 梢,マーメイドグリーン,#68BE8D,両日
ll,蓮ノ空女学院スクールアイドルクラブ,佐々木琴子,夕霧綴理,ボクの赤,#BA2636,両日
ll,蓮ノ空女学院スクールアイドルクラブ,菅 叶和,大沢瑠璃乃,瑠璃ピンク,#E7609E,両日
ll,蓮ノ空女学院スクールアイドルクラブ,月音こな,藤島 慈,エンジェルホワイト,#C8C2C6,両日
imas,シャイニーカラーズ,礒部花凜,月岡恋鐘,,#f84cad,day1
imas,シャイニーカラーズ,菅沼千紗,田中摩美々,,#a846fb,day1
imas,シャイニーカラーズ,八巻アンナ,白瀬咲耶,,#006047,day1
imas,シャイニーカラーズ,希水しお,三峰結華,,#3b91c4,day1
imas,シャイニーカラーズ,結名美月,幽谷霧子,,#d9f2ff,day1
imas,シャイニーカラーズ,黒木ほの香,大崎甘奈,,#f54275,day1
imas,シャイニーカラーズ,前川涼子,大崎甜花,,#e75bec,day1
imas,シャイニーカラーズ,芝崎典子,桑山千雪,,#fafafa,day1
imas,シャイニーカラーズ,和久井 優,浅倉 透,,#50d0d0,day1
imas,シャイニーカラーズ,土屋李央,樋口円香,,#be1e3e,day1
imas,シャイニーカラーズ,田嶌紗蘭,福丸小糸,,#7967c3,day1
imas,シャイニーカラーズ,岡咲美保,市川雛菜,,#ffc639,day1
imas,シャイニーカラーズ,紫月杏朱彩,七草にちか,,#a6cdb6,day1
imas,シャイニーカラーズ,山根 綺,緋田美琴,,#760f10,day1
imas,シャイニーカラーズ,関根 瞳,櫻木真乃,,#ffbad6,day2
imas,シャイニーカラーズ,近藤玲奈,風野灯織,,#144384,day2
imas,シャイニーカラーズ,峯田茉優,八宮めぐる,,#ffe012,day2
imas,シャイニーカラーズ,河野ひより,小宮果穂,,#e5461c,day2
imas,シャイニーカラーズ,白石晴香,園田智代子,,#f93b90,day2
imas,シャイニーカラーズ,永井真里子,西城樹里,,#ffc602,day2
imas,シャイニーカラーズ,丸岡和佳奈,杜野凛世,,#89c3eb,day2
imas,シャイニーカラーズ,涼本あきほ,有栖川夏葉,,#90e667,day2
imas,シャイニーカラーズ,田中有紀,芹沢あさひ,,#f30100,day2
imas,シャイニーカラーズ,幸村恵理,黛 冬優子,,#5aff19,day2
imas,シャイニーカラーズ,北原沙弥香,和泉愛依,,#ff00ff,day2
imas,シャイニーカラーズ,川口莉奈,斑鳩ルカ,,#23120c,day2
imas,シャイニーカラーズ,三川華月,鈴木羽那,,#e4cad5,day2
imas,シャイニーカラーズ,小澤麗那,郁田はるき,,#f8e5b2,day2
imas,ミリオンライブ！,山崎はるか,春日未来,,#ea5b76,day1
imas,ミリオンライブ！,田所あずさ,最上静香,,#6495cf,day1
imas,ミリオンライブ！,Machico,伊吹 翼,,#fed552,day1
imas,ミリオンライブ！,麻倉もも,箱崎星梨花,,#ed90ba,day1
imas,ミリオンライブ！,小岩井ことり,天空橋朋花,,#bee3e3,day1
imas,ミリオンライブ！,中村温姫,ロコ,,#fff03c,day1
imas,ミリオンライブ！,平山笑美,北上麗花,,#6bb6b0,day1
imas,ミリオンライブ！,渡部優衣,横山奈緒,,#788bc5,day1
imas,ミリオンライブ！,愛美,ジュリア,,#d7385f,day2
imas,ミリオンライブ！,伊藤美来,七尾百合子,,#c7b83c,day2
imas,ミリオンライブ！,木戸衣吹,矢吹可奈,,#f5ad3b,day2
imas,ミリオンライブ！,香里有佐,桜守歌織,,#274079,day2
imas,ミリオンライブ！,駒形友梨,高山紗代子,,#7f6575,day2
imas,ミリオンライブ！,末柄里恵,豊川風花,,#7278a8,day2
imas,ミリオンライブ！,南 早紀,白石 紬,,#ebe1ff,day2
imas,ミリオンライブ！,山口立花子,百瀬莉緒,,#f19591,day2`;

import { ref } from "vue";
const day = new URL(window.location.href).searchParams.get("day") == 2 ? 2 : 1;

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

const colorNameCheck = ref(false);

function colorHint(e) {
  if (colorNameCheck.value) {
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
