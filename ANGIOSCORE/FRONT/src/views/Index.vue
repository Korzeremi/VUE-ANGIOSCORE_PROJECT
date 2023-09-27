<script setup>
</script>

<template>
    <body>
        <div class="index-title">
            <p>ANGIOSCORE</p>
        </div>
        <div class="index-table">
            <div class="index-table-r">
                <div class="index-table-r-title">
                    <h1>R</h1>
                </div>
                <div class="index-table-r-row">
                    <div class="index-table-r1">
                        <label for="r1">R1</label>
                        <input type="checkbox" name="r1" id="r1" value="r1" v-model="r1Selected">
                    </div>
                    <div class="index-table-r2">
                        <label for="r2">R2</label>
                        <input type="checkbox" name="r2" id="r2" value="r2" v-model="r2Selected">
                    </div>
                    <div class="index-table-r3">
                        <label for="r3">R3</label>
                        <input type="checkbox" name="r3" id="r3" value="r3" v-model="r3Selected">
                    </div>
                </div>
            </div>
            <div class="index-table-s">
                <div class="index-table-s-title">
                    <h1>S</h1>
                </div>
                <div class="index-table-s-row">
                    <div class="index-table-s1">
                        <label for="s1">S1</label>
                        <input type="checkbox" name="S1" id="S1" value="S1" v-model="s1Selected">
                    </div>
                    <div class="index-table-s2">
                        <label for="s2">S2</label>
                        <input type="checkbox" name="s2" id="s2" value="s2" v-model="s2Selected">
                    </div>
                    <div class="index-table-s3">
                        <label for="s3">S3</label>
                        <input type="checkbox" name="s3" id="s3" value="s3" v-model="s3Selected">
                    </div>
                </div>
            </div>
            <div class="index-table-v">
                <div class="index-table-v-title">
                    <h1>V</h1>
                </div>
                <div class="index-table-v-row">
                    <div class="index-table-v1">
                        <label for="v1">V1</label>
                        <input type="checkbox" name="v1" id="v1" value="v1" v-model="v1Selected">
                    </div>
                    <div class="index-table-r2">
                        <label for="v2">V2</label>
                        <input type="checkbox" name="v2" id="v2" value="v2" v-model="v2Selected">
                    </div>
                    <div class="index-table-v3">
                        <label for="v3">V3</label>
                        <input type="checkbox" name="v3" id="v3" value="v3" v-model="v3Selected">
                    </div>
                </div>
            </div>

        </div>
        <div class="index-btn">
            <button @click="afficherResultat">
                <p>Voir le résultat</p>
            </button>
        </div>
        <div class="index-result">
            <p v-if="resultValue !== 'NULL'">{{ resultValue.trim() }}</p>
        </div>
    </body>
</template>

<script>
export default {
  data() {
    return {
      r1Selected: false,
      r2Selected: false,
      r3Selected: false,
      s1Selected: false,
      s2Selected: false,
      s3Selected: false,
      v1Selected: false,
      v2Selected: false,
      v3Selected: false,
      resultValue: 'NULL'
    };
  },
  methods: {
    afficherResultat() {
      console.log("Bouton");
      let resultat = '';
      if (this.r1Selected) {
          resultat += 'r1';
      }
      if (this.r2Selected) {
          resultat += 'r2';
      }
      if (this.r3Selected) {
          resultat += 'r3';
      }
      if (this.s1Selected) {
          resultat += 's1';
      }
      if (this.s2Selected) {
          resultat += 's2';
      }
      if (this.s3Selected) {
          resultat += 's3';
      }
      if (this.v1Selected) {
          resultat += 'v1';
      }
      if (this.v2Selected) {
          resultat += 'v2';
      }
      if (this.v3Selected) {
          resultat += 'v3';
      }
      this.resultValue = resultat;
      console.log(this.resultValue);
    }
  }
};
</script>

<style src="/src/style/Index.scss"></style>