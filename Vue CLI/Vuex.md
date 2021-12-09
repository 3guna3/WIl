## Vuexとは

- VuexはVue.jsアプリケーションで最もよく使われている**状態管理ライブラリ**
- コンポーネント間で状態を共有するための仕組みが状態管理
- 状態管理ではデータを１つの「ストア」に集約し、どのコンポーネントからもストアを参照できるようにすることで、値の受け渡しをシンプルにする

### Flux

- Vuexは**Flux**という状態管理のアーキテクチャに基づいている
- Fluxは状態管理のための一方通行のデータフローのアーキテクチャである
  - 管理しているデータは「State」が保持しており、コンポーネントはこのStateをrenderして値を取得する
  - Stateで管理しているデータを更新する場合は、「Action」を呼び出す(dispatchする)ことで指示を与える
  - ActionはAPIを呼び出してデータを取得するなどの**非同期処理**を行う
    - ActionではまだStateを変更せず、「Mutation」の呼び出しを行う
  - MutationではActionから値を受け取り、Stateの更新(mutate)を行う
    - Stateの値を更新できるのはこのMutationのみ

このように、状態を変化させる処理を「Action」「Mutation」「State」に役割分担し、データを循環させるように管理する仕組みとなっている


## Vuexを使ってコンポーネント間でデータを共有する
- 状態管理を行うためには **「store」が必要**

### ストアの作成
- `store`ディレクトリの中に`modules`ディレクトリを作成し、その中に`hoge.js`を作成する

**hoge.js**
```js
import axios from 'axios'

const apiUrl = 'http://localhost:3000';

// state(状態管理するデータ)の定義
const state = {
  hoges: []
}

// gtters(stateの値を取り出す関数)の定義
const getters = {
  hoges: state => state.hoges
}

// mutations(hogesデータをstateに保存する関数)の定義
const mutations = {
  setHoges: (state, hoges) => (state.hoges = hoges)
}

// actions(axiosでAPIリクエストを送信してhogesデータを取得し、mutationsを呼び出す関数)を定義
const actions = {
  async fetchHoges({ commit }) {
    const response = await axios.get(`${apiUrl}/events`);
    // mutationの呼び出し
    commit('setHoges', response.data);
  }
 }
 
 export default {
  namespaced: true,
  state,
  getters,
  mutations,
  actions
 };
```
「state」 「getters」 「mutations」　「actions」　の4つが必要

- state
  - 状態を管理するデータを定義する
- getters 
  - stateの値を取り出す関数を定義する
- mutations
  - eventsデータをstateに保存する関数を定義する
- actions
  - axiosでAPIリクエストを送信してデータを取得し、mutationsを呼び出す関数を定義する


「state」 「getters」 「mutations」　「actions」　の4つが必要dエータを定義する
「state」 「getters」 「mutations」　「actions」　の4つが必要
