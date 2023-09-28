<script setup>
</script>

<template>
    <body>
        <div class="blur-sct"></div>
        <img src="../assets/wp.jpg" alt="wp">
        <div class="index-app">
            <div class="index-title">
                <p>ANGIOSCORE</p>
                <h4>Classification Tools for Angiologists</h4>
            </div>
            <div class="index-sep"></div>
            <div class="index-name">
                <!-- <p>Patient's name :</p> -->
                <input type="text" placeholder="Patient's name" id="patN" v-model="patIn">
            </div>
            <div class="index-sep"></div>
            <div class="index-table">
                <div class="index-svp">
                    <div class="index-svp-title">
                        <p>Symptoms-Varices-Pathophysiology (SVP)</p>
                        <button class="SVP-DP-btn" @click="SVPDrop">OFF/ON</button>
                    </div>
                    <div class="index-svp-select">
                        <div class="index-svp-select-S">
                            <button class="s-dropdown-button" @click="StoggleDropdown">Symptoms (S)</button>
                            <select multiple id="s-dropdown" class="s-dropdown-content" style="display: none;" v-model="sDrop" @change="ShowResult">
                                <option value="0">No pelvic symptoms</option>
                                <option value="1">Renal</option>
                                <option value="2">Pelvic</option>
                                <option value="3">Extrapelvic</option>
                                <option value="3a">Genital</option>
                                <option value="3b">Leg symptoms</option>
                                <option value="3c">Venous claudication</option>
                            </select>
                        </div>
                        <div class="index-svp-select-V">
                            <button class="v-dropdown-button" @click="VtoggleDropdown">Varices (V)</button>
                            <select multiple id="v-dropdown" class="v-dropdown-content" style="display: none;" v-model="vDrop" @change="ShowResult">
                                <option value="0">No pelvic varices</option>
                                <option value="1">Renal</option>
                                <option value="2">Pelvic</option>
                                <option value="3">Extrapelvic</option>
                                <option value="3a">Genital</option>
                                <option value="3b">Leg varices</option>
                            </select>
                        </div>
                        <div class="index-svp-select-P">
                            <button class="p-dropdown-button" @click="PtoggleDropdown">Anatomy/pathophysiology (P)</button>
                            <select multiple id="p-dropdown" class="p-dropdown-content" style="display: none;" v-model="pDrop" @change="ShowResult">
                                <option value="IVCOT">-IVC-O-T</option>
                                <option value="NT">---NT</option>
                                <option value="C">---C</option>
                                <option value="LRVOT">L-RV-O-T</option>
                                <option value="RGVOT">R-GV-O-T</option>
                                <option value="LRNT">L-RNT</option>
                                <option value="BC">B--C</option>
                                <option value="RCIVOT">R-CIV-O-T</option>
                                <option value="RIIVOT">R-IIV-O-T</option>
                                <option value="REIVOT">R-EIV-O-T</option>
                                <option value="RPELVOT">R-PELV-O-T</option>
                                <option value="P">P---</option>
                            </select>
                        </div>
                    </div>
                </div>
                <div class="index-ceap">
                    <div class="index-ceap-title">
                        <p>Clinical Etiologic Anatomic Pathophysiologic (CEAP)</p>
                        <button class="CEAP-DP-btn" @click="CEAPDrop">OFF/ON</button>
                    </div>
                    <div class="index-ceap-select">
                        <div class="index-ceap-select-C">
                            <button class="C-dropdown-button" @click="CtoggleDropdown">Clinical</button>
                            <select multiple id="C-dropdown" class="C-dropdown-content" style="display: none;" v-model="CDrop">         
                                <option value="C0">C0</option>
                                <option value="C1">C1</option>
                                <option value="C2">C2</option>
                                <option value="C3">C3</option>
                                <option value="C4">C4</option>
                                <option value="C4a">C4a</option>
                                <option value="C4b">C4b</option>
                                <option value="C5">C5</option>
                                <option value="C6">C6</option>
                            </select>
                        </div>
                        <div class="index-ceap-select-E">
                            <button class="E-dropdown-button" @click="EtoggleDropdown">Etiologic</button>
                            <select multiple id="E-dropdown" class="E-dropdown-content" style="display: none;" v-model="EDrop">         
                                <option value="Ec">Ec</option>
                                <option value="Ep">Ep</option>
                                <option value="Es">Es</option>
                                <option value="En">En</option>
                            </select>
                        </div>
                        <div class="index-ceap-select-A">
                            <button class="A-dropdown-button" @click="AtoggleDropdown">Anatomic</button>
                            <div class="index-ceap-select-Ax">
                                <select multiple id="A1-dropdown" class="A1-dropdown-content" style="display: none;" v-model="A1Drop">         
                                    <option value="As">As</option>
                                    <option value="Ad">Ad</option>
                                    <option value="Ap">Ap</option>
                                    <option value="An">An</option>
                                </select>
                                <select multiple id="A2-dropdown" class="A2-dropdown-content" style="display: none;" v-model="A2Drop">         
                                    <option value="1">1</option>
                                    <option value="2">2</option>
                                    <option value="3">3</option>
                                    <option value="4">4</option>
                                    <option value="5">5</option>
                                    <option value="6">6</option>
                                    <option value="7">7</option>
                                    <option value="8">8</option>
                                    <option value="9">9</option>
                                    <option value="10">10</option>
                                    <option value="11">11</option>
                                    <option value="12">12</option>
                                    <option value="13">13</option>
                                    <option value="14">14</option>
                                    <option value="15">15</option>
                                    <option value="16">16</option>
                                    <option value="17">17</option>
                                    <option value="18">18</option>
                                </select>
                            </div>
                        </div>
                        <div class="index-ceap-select-P">
                            <button class="P2-dropdown-button" @click="P2toggleDropdown">Pathophysiologic</button>
                            <select multiple id="P2-dropdown" class="P2-dropdown-content" style="display: none;" v-model="PDrop">         
                                <option value="Pr">Pr</option>
                                <option value="Po">Po</option>
                                <option value="Pro">Pro</option>
                                <option value="Pn">Pn</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
            <div class="index-sep"></div>
            <div class="index-results">
                <div class="index-svp-result">
                    <p class="svp-p">SVP</p>
                    <p v-if="resultValueSVP !== 'NULL'">: {{ resultValueSVP }}</p>
                </div>
                <div class="index-ceap-result">
                    <p class="ceap-p">CEAP</p>
                    <p v-if="resultValueCEAP !== 'NULL'">: {{ resultValueCEAP }}</p>
                </div>
                <div class="index-results-btn">
                    <button @click="EraseName">CLEAR NAME</button>   
                    <button @click="EraseSVP">CLEAR SVP</button>   
                    <button @click="EraseCEAP">CLEAR CEAP</button> 
                    <button @click="Save">SAVE SCORES</button>  
                </div>
            </div>
            <div class="index-sep"></div>

        </div>
    </body>
</template>

<script>
export default {
  data() {
    return {
        patIn: '',
        sDrop: [],
        vDrop: [],
        pDrop: [],
        resultValueSVP: 'NULL',
        CDrop: [],
        EDrop: [],
        A1Drop: [],
        A2Drop: [],
        PDrop: [],
        resultValueCEAP: 'NULL',
    };
  },
  watch: {
    sDrop: 'ShowResultSVP',
    vDrop: 'ShowResultSVP',
    pDrop: 'ShowResultSVP',
    CDrop: 'ShowResultCEAP',
    EDrop: 'ShowResultCEAP',
    A1Drop: 'ShowResultCEAP',
    A2Drop: 'ShowResultCEAP',
    PDrop: 'ShowResultCEAP',
  },
  methods: {
    SVPDrop(){
        var Dropdown1 = document.getElementById("s-dropdown");
        var Dropdown2 = document.getElementById("v-dropdown");
        var Dropdown3 = document.getElementById("p-dropdown");
        if (Dropdown1.style.display === "none" && Dropdown2.style.display === "none" && Dropdown3.style.display === "none") {
            Dropdown1.style.display = "block";
            Dropdown2.style.display = "block";
            Dropdown3.style.display = "block";
        } else {
            Dropdown1.style.display = "none";
            Dropdown2.style.display = "none";
            Dropdown3.style.display = "none";
        };
    },
    CEAPDrop(){
        var DropdownA = document.getElementById("C-dropdown");
        var DropdownE = document.getElementById("E-dropdown");
        var DropdownA1 = document.getElementById("A1-dropdown");
        var DropdownA2 = document.getElementById("A2-dropdown");
        var DropdownP2 = document.getElementById("P2-dropdown");
        if (DropdownA.style.display === "none" && DropdownE.style.display === "none" && DropdownA1.style.display === "none" && DropdownA2.style.display === "none" && DropdownP2.style.display === "none") {
            DropdownA.style.display = "block";
            DropdownA1.style.display = "block";
            DropdownA2.style.display = "block";
            DropdownE.style.display = "block";
            DropdownP2.style.display = "block";
        } else {
            DropdownA.style.display = "none";
            DropdownA1.style.display = "none";
            DropdownA2.style.display = "none";
            DropdownE.style.display = "none";
            DropdownP2.style.display = "none";
        };
    },
    StoggleDropdown() {
        var Dropdown = document.getElementById("s-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    VtoggleDropdown() {
        var Dropdown = document.getElementById("v-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    PtoggleDropdown() {
        var Dropdown = document.getElementById("p-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    CtoggleDropdown() {
        var Dropdown = document.getElementById("C-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    EtoggleDropdown() {
        var Dropdown = document.getElementById("E-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    AtoggleDropdown() {
        var Dropdown1 = document.getElementById("A1-dropdown");
        var Dropdown2 = document.getElementById("A2-dropdown");
        if (Dropdown1.style.display === "none") {
            Dropdown1.style.display = "block";
        } else {
            Dropdown1.style.display = "none";
        }
        if (Dropdown2.style.display === "none") {
            Dropdown2.style.display = "block";
        } else {
            Dropdown2.style.display = "none";
        }
    },
    P2toggleDropdown() {
        var Dropdown = document.getElementById("P2-dropdown");
        if (Dropdown.style.display === "none") {
            Dropdown.style.display = "block";
        } else {
            Dropdown.style.display = "none";
        }
    },
    ShowResultSVP() {
        const selectedValuesSVP = [...this.sDrop, ...this.vDrop, ...this.pDrop];
        this.resultValueSVP = selectedValuesSVP.join('');
    },
    ShowResultCEAP() {
        const selectedValuesCEAP = [...this.CDrop, ...this.EDrop, ...this.A1Drop, ...this.A2Drop, ...this.PDrop];
        this.resultValueCEAP = selectedValuesCEAP.join('');
    },
    EraseSVP() {
        this.selectedValuesSVP = '';
        this.sDrop = [];
        this.vDrop = [];
        this.pDrop = [];
    },
    EraseCEAP() {
        this.selectedValuesCEAP = '';
        this.CDrop = [];
        this.EDrop = [];
        this.A1Drop = [];
        this.A2Drop = [];
        this.PDrop = [];
    },
    EraseName() {
        this.patIn = '';
    },
    Save() {
        const name = this.patIn;
        const savedResult = `ANGIOSCORE\n-------------------------\nPatient's name : ${name}\nSVP : ${this.resultValueSVP}\nCEAP : ${this.resultValueCEAP}\n-------------------------\nBy LemnixTech\n-------------------------`;
        const blob = new Blob([savedResult], { type: 'text/plain'});
        const url = window.URL.createObjectURL(blob);
        const file = document.createElement('a');
        const cDate = new Date();
        const fileName = `angioscore_${cDate.toLocaleString().replace(/[/: ,]+/g, "_")}.txt`;
        file.style.display = 'none';
        file.href  = url;
        file.download = fileName;
        document.body.appendChild(file);
        file.click();
        window.URL.revokeObjectURL(url);
        document.body.removeChild(file);
    }
  }
};
</script>

<style src="/src/style/Index.scss"></style>