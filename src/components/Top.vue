<template>
  <div>
    <section>
      <h1>takumiabe.github.io</h1>
      自分がやったことを覚えておくためのページ
    </section>
    <section v-for="item in items" :key="item.name">
      <h1><a :href="item.url">{{item.name}}</a></h1>
      <p v-for="(line, index) in item.desc" :key="index">{{line}}</p>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          name: 'cartographer',
          url: 'https://github.com/takumiabe/cartographer',
          desc: [
            `terraformをプロダクションで使ってたときに、`,
            `運用ドキュメントとしてインスタンスの関連図が欲しくなったので作成。`,
            `terraform v0.9.0ぐらいの頃作った。`,
            `ネットワーク系の入れ子構造をgraphvizで上手に表現できずにイマイチなところで放棄`,
            `providerはAWSにしか対応してない。`
          ]
        },
        {
          name: 'influxdb-swift',
          url: 'https://github.com/takumiabe/influxdb-swift',
          desc: [
            `MacOSアプリからinfluxdbという時系列データベースを叩くのに作った。`,
            `ものの試しってことでswiftで書いたんだけど、`,
            `この頃のswiftは確かまだ2.0ぐらいで全然こなれてなかったはず。`,
            `自分もswiftには慣れてなかったし、企画も無くなってしまったので放置。`
          ]
        },
        {
          name: 'migration_comments',
          url: 'https://github.com/takumiabe/migration_comments/tree/prev',
          desc: [
            `forkしたもの。`,
            `とあるRailsプロジェクトでannotateと組み合わせて使ってたんだけど、`,
            `改行を含むコメントに対する挙動の修正を試みたもの`,
            `コードリーディングからの、パッチを作ってみるところまではいったものの、`,
            `動作確認してしっかり動くの確認したらPRにしようかな…と思っていたら、`,
            `Railsの公式対応が(しかも部分的に)入ってしまった。うーん。`
          ]
        },
        {
          name: 'readablecode_lesson',
          url: 'https://github.com/takumiabe/readablecode_lesson',
          desc: [
            `書籍「リーダブルコード」の社内勉強会で出題する演習問題。`,
            `同僚と交代交代でがんばった。`
          ]
        },
        {
          name: 'editorconfig-emacs',
          url: 'https://github.com/takumiabe/editorconfig-emacs',
          desc: [
            `forkしたもの。`,
            `editorconfigに感銘を受けて、このパッケージ(elisp)を使い始めたが、`,
            `character=が対応してなかったので対応させたもの。`,
            `のはずなんだけど、動いてたかどうか自信がない。`,
            `今はもうemacsは使ってないので、確かめようがない…`
          ]
        },
        {
          name: 'rspec-formatter-documentation_travis_ci',
          url: 'https://github.com/takumiabe/rspec-formatter-documentation_travis_ci',
          desc: [
            `travis-ci用になんかいい感じにtravis用のタグを吐く、RSpecのformatter。`,
            `travis-ciのログは、travis_fold:start / travis_fold:end というログを吐くと、`,
            `その箇所を折りたためるようにしてくれる。`,
            `コレを使って、RSpecの「Documentation」モードのフォーマッタを折りたためるようにした。`,
            `結局CI上では、通常のprogress表示(dotが増えてゆくやつ)のほうが`,
            `わかりやすくて自分でも使わなくなってしまった。`
          ]
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
section {
  margin-left: 2em;
}
section p {
  margin-left: 2em;
}
a {
  color: #42b983;
}
</style>
