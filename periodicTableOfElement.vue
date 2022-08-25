<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import { reactive, ref } from "vue";
// let electronics = ref(["K","L","M","N","O","P"])
let electronics = ref(["P", "O", "N", "M", "L", "K"]);
let electronicsNum = ref([8, 18, 32, 18, 8, 2]);
let LaSeries = ref([
  {
    index: 57,
    chemicalymbol: "La",
    chemicalName: "镧",
    valenceElectron: "5d<sup>1</sup>6s<sup>2</sup>",
    relativeAtomicMass: 138.9,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 58,
    chemicalymbol: "Ce",
    chemicalName: "铈",
    valenceElectron: "4f<sup>1</sup>5d<sup>1</sup>6s<sup>2</sup>",
    relativeAtomicMass: 140.1,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 59,
    chemicalymbol: "Pr",
    chemicalName: "镨",
    valenceElectron: "4f<sup>3</sup>6s<sup>2</sup>",
    relativeAtomicMass: 140.9,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 60,
    chemicalymbol: "Nd",
    chemicalName: "钕",
    valenceElectron: "4f<sup>4</sup>6s<sup>2</sup>",
    relativeAtomicMass: 144.2,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 61,
    chemicalymbol: "Pm",
    chemicalName: "钷",
    valenceElectron: "4f<sup>5</sup>6s<sup>2</sup>",
    relativeAtomicMass: 145,
    metallic: true,
    radioactivity: true,
  },
  {
    index: 62,
    chemicalymbol: "Sm",
    chemicalName: "钐",
    valenceElectron: "4f<sup>6</sup>6s<sup>2</sup>",
    relativeAtomicMass: 150.4,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 63,
    chemicalymbol: "Eu",
    chemicalName: "铕",
    valenceElectron: "4f<sup>7</sup>6s<sup>2</sup>",
    relativeAtomicMass: 152.0,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 64,
    chemicalymbol: "Gd",
    chemicalName: "钆",
    valenceElectron: "4f<sup>7</sup>5d<sup>1</sup>6s<sup>2</sup>",
    relativeAtomicMass: 157.3,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 65,
    chemicalymbol: "Td",
    chemicalName: "铽",
    valenceElectron: "4f<sup>9</sup>6s<sup>2</sup>",
    relativeAtomicMass: 158.9,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 66,
    chemicalymbol: "Dy",
    chemicalName: "镝",
    valenceElectron: "4f<sup>10</sup>6s<sup>2</sup>",
    relativeAtomicMass: 162.5,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 67,
    chemicalymbol: "Ho",
    chemicalName: "钬",
    valenceElectron: "4f<sup>11</sup>6s<sup>2</sup>",
    relativeAtomicMass: 158.9,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 68,
    chemicalymbol: "Er",
    chemicalName: "铒",
    valenceElectron: "4f<sup>12</sup>6s<sup>2</sup>",
    relativeAtomicMass: 167.3,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 69,
    chemicalymbol: "Tm",
    chemicalName: "铥",
    valenceElectron: "4f<sup>13</sup>6s<sup>2</sup>",
    relativeAtomicMass: 168.9,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 70,
    chemicalymbol: "Yb",
    chemicalName: "镱",
    valenceElectron: "4f<sup>14</sup>6s<sup>2</sup>",
    relativeAtomicMass: 173.0,
    metallic: true,
    radioactivity: false,
  },
  {
    index: 71,
    chemicalymbol: "Lu",
    chemicalName: "镥",
    valenceElectron: "4f<sup>14</sup>5d<sup>1</sup>6s<sup>2</sup>",
    relativeAtomicMass: 175.0,
    metallic: true,
    radioactivity: false,
  },
]);

let AcSeries = ref([
  {
    index: 89,
    chemicalymbol: "Ac",
    chemicalName: "锕",
    valenceElectron: "6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔227〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 90,
    chemicalymbol: "Th",
    chemicalName: "钍",
    valenceElectron: "6d<sup>2</sup>7s<sup>2</sup>",
    relativeAtomicMass: 232.0,
    metallic: true,
    radioactivity: true,
  },
  {
    index: 91,
    chemicalymbol: "Pa",
    chemicalName: "幞",
    valenceElectron: "5f<sup>2</sup>6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass:231.0,
    metallic: true,
    radioactivity: true,
  },
  {
    index: 92,
    chemicalymbol: "U",
    chemicalName: "铀",
    valenceElectron: "5f<sup>3</sup>6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass: 238.0,
    metallic: true,
    radioactivity: true,
  },
  {
    index: 93,
    chemicalymbol: "Np",
    chemicalName: "镎",
    valenceElectron: "5f<sup>4</sup>6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔237〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 94,
    chemicalymbol: "Pu",
    chemicalName: "钚",
    valenceElectron: "5f<sup>6</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔244〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 95,
    chemicalymbol: "Am",
    chemicalName: "镅*",
    valenceElectron: "5f<sup>7</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔243〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 96,
    chemicalymbol: "Cm",
    chemicalName: "锔*",
    valenceElectron: "5f<sup>7</sup>6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔247〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 97,
    chemicalymbol: "Bk",
    chemicalName: "锫*",
    valenceElectron: "5f<sup>9</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔247〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 98,
    chemicalymbol: "Cf",
    chemicalName: "锎*",
    valenceElectron: "5f<sup>10</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔251〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 99,
    chemicalymbol: "Es",
    chemicalName: "锿*",
    valenceElectron: "5f<sup>11</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔252〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 100,
    chemicalymbol: "Fm",
    chemicalName: "镄*",
    valenceElectron: "5f<sup>12</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔257〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 101,
    chemicalymbol: "Md",
    chemicalName: "钔*",
    valenceElectron: "5f<sup>13</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔258〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 102,
    chemicalymbol: "No",
    chemicalName: "锘*",
    valenceElectron: "5f<sup>14</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔259〕",
    metallic: true,
    radioactivity: true,
  },
  {
    index: 103,
    chemicalymbol: "Lr",
    chemicalName: "铹",
    valenceElectron: "5f<sup>14</sup>6d<sup>1</sup>7s<sup>2</sup>",
    relativeAtomicMass: "〔262〕",
    metallic: true,
    radioactivity: true,
  },
]);

let tableData = ref({
  IA: [
    {
      index: 1,
      chemicalymbol: "H",
      chemicalName: "氢",
      valenceElectron: "1s<sup>1</sup>",
      relativeAtomicMass: 1.008,
      metallic: false,
    },
    {
      index: 3,
      chemicalymbol: "Li",
      chemicalName: "锂",
      valenceElectron: "2s<sup>1</sup>",
      relativeAtomicMass: 6.941,
      metallic: true,
    },
    {
      index: 11,
      chemicalymbol: "Na",
      chemicalName: "钠",
      valenceElectron: "3s<sup>1</sup>",
      relativeAtomicMass: 22.99,
      metallic: true,
    },
    {
      index: 19,
      chemicalymbol: "K",
      chemicalName: "钾",
      valenceElectron: "4s<sup>1</sup>",
      relativeAtomicMass: 39.1,
      metallic: true,
    },
    {
      index: 37,
      chemicalymbol: "Rb",
      chemicalName: "铷",
      valenceElectron: "5s<sup>1</sup>",
      relativeAtomicMass: 85.47,
      metallic: true,
    },
    {
      index: 55,
      chemicalymbol: "Cs",
      chemicalName: "铯",
      valenceElectron: "6s<sup>1</sup>",
      relativeAtomicMass: 132.9,
      metallic: true,
    },
    {
      index: 87,
      chemicalymbol: "Fr",
      chemicalName: "钫",
      valenceElectron: "7s<sup>1</sup>",
      relativeAtomicMass: "〔223〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  IIA: [
    {
      index: 4,
      chemicalymbol: "Be",
      chemicalName: "铍",
      valenceElectron: "2s<sup>2</sup>",
      relativeAtomicMass: 9.012,
      metallic: true,
    },
    {
      index: 12,
      chemicalymbol: "Mg",
      chemicalName: "镁",
      valenceElectron: "3s<sup>2</sup>",
      relativeAtomicMass: 24.31,
      metallic: true,
    },
    {
      index: 20,
      chemicalymbol: "Ca",
      chemicalName: "钙",
      valenceElectron: "4s<sup>2</sup>",
      relativeAtomicMass: 40.08,
      metallic: true,
    },
    {
      index: 38,
      chemicalymbol: "Sr",
      chemicalName: "锶",
      valenceElectron: "5s<sup>2</sup>",
      relativeAtomicMass: 87.62,
      metallic: true,
    },
    {
      index: 56,
      chemicalymbol: "Ba",
      chemicalName: "钡",
      valenceElectron: "6s<sup>2</sup>",
      relativeAtomicMass: 137.3,
      metallic: true,
    },
    {
      index: 88,
      chemicalymbol: "Ra",
      chemicalName: "镭",
      valenceElectron: "7s<sup>2</sup>",
      relativeAtomicMass: "〔226〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  IIIB: [
    {
      index: 21,
      chemicalymbol: "Sc",
      chemicalName: "钪",
      valenceElectron: "3d<sup>1</sup>4s<sup>2</sup>",
      relativeAtomicMass: 44.96,
      metallic: true,
    },
    {
      index: 39,
      chemicalymbol: "Y",
      chemicalName: "钇",
      valenceElectron: "4d<sup>1</sup>5s<sup>2</sup>",
      relativeAtomicMass: 88.91,
      metallic: true,
    },
    {
      index: "57~71",
      chemicalymbol: "La~Lu",
      chemicalName: "镧系",
      valenceElectron: "",
      relativeAtomicMass: "",
      metallic: true,
    },
    {
      index: "89~103",
      chemicalymbol: "Ac~Lr",
      chemicalName: "锕系",
      valenceElectron: "",
      relativeAtomicMass: "",
      metallic: true,
    },
  ],
  IVB: [
    {
      index: 22,
      chemicalymbol: "Ti",
      chemicalName: "钛",
      valenceElectron: "3d<sup>2</sup>4s<sup>2</sup>",
      relativeAtomicMass: 44.96,
      metallic: true,
    },
    {
      index: 39,
      chemicalymbol: "Zr",
      chemicalName: "锆",
      valenceElectron: "4d<sup>2</sup>5s<sup>2</sup>",
      relativeAtomicMass: 91.22,
      metallic: true,
    },
    {
      index: 72,
      chemicalymbol: "Hf",
      chemicalName: "铪",
      valenceElectron: "5d<sup>2</sup>6s<sup>2</sup>",
      relativeAtomicMass: 178.5,
      metallic: true,
    },
    {
      index: 104,
      chemicalymbol: "Rf",
      chemicalName: "钅卢*",
      valenceElectron: "6d<sup>2</sup>7s<sup>2</sup>",
      relativeAtomicMass: "〔261〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VB: [
    {
      index: 23,
      chemicalymbol: "V",
      chemicalName: "钒",
      valenceElectron: "3d<sup>3</sup>4s<sup>2</sup>",
      relativeAtomicMass: 50.94,
      metallic: true,
    },
    {
      index: 41,
      chemicalymbol: "Nb",
      chemicalName: "铌",
      valenceElectron: "4d<sup>4</sup>5s<sup>1</sup>",
      relativeAtomicMass: 92.91,
      metallic: true,
    },
    {
      index: 73,
      chemicalymbol: "Ta",
      chemicalName: "钽",
      valenceElectron: "5d<sup>3</sup>6s<sup>2</sup>",
      relativeAtomicMass: 180.9,
      metallic: true,
    },
    {
      index: 105,
      chemicalymbol: "Db",
      chemicalName: "钅杜*",
      valenceElectron: "6d<sup>3</sup>7s<sup>2</sup>",
      relativeAtomicMass: "〔262〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VIB: [
    {
      index: 24,
      chemicalymbol: "Cr",
      chemicalName: "铬",
      valenceElectron: "3d<sup>5</sup>4s<sup>1</sup>",
      relativeAtomicMass: 52.0,
      metallic: true,
    },
    {
      index: 42,
      chemicalymbol: "Mo",
      chemicalName: "钼",
      valenceElectron: "4d<sup>5</sup>5s<sup>1</sup>",
      relativeAtomicMass: 95.94,
      metallic: true,
    },
    {
      index: 74,
      chemicalymbol: "W",
      chemicalName: "钨",
      valenceElectron: "5d<sup>4</sup>6s<sup>2</sup>",
      relativeAtomicMass: 183.8,
      metallic: true,
    },
    {
      index: 106,
      chemicalymbol: "Sg",
      chemicalName: "钅喜*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔266〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VIIB: [
    {
      index: 25,
      chemicalymbol: "Mn",
      chemicalName: "锰",
      valenceElectron: "3d<sup>5</sup>4s<sup>2</sup>",
      relativeAtomicMass: 54.94,
      metallic: true,
    },
    {
      index: 43,
      chemicalymbol: "Tc",
      chemicalName: "锝",
      valenceElectron: "4d<sup>5</sup>5s<sup>2</sup>",
      relativeAtomicMass: "〔98〕",
      metallic: true,
      radioactivity: true,
    },
    {
      index: 75,
      chemicalymbol: "Re",
      chemicalName: "铼",
      valenceElectron: "5d<sup>5</sup>6s<sup>2</sup>",
      relativeAtomicMass: 186.2,
      metallic: true,
    },
    {
      index: 107,
      chemicalymbol: "Bh",
      chemicalName: "钅波*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔264〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VIIIa: [
    {
      index: 26,
      chemicalymbol: "Fe",
      chemicalName: "铁",
      valenceElectron: "3d<sup>6</sup>4s<sup>2</sup>",
      relativeAtomicMass: 55.85,
      metallic: true,
    },
    {
      index: 44,
      chemicalymbol: "Ru",
      chemicalName: "钌",
      valenceElectron: "4d<sup>7</sup>5s<sup>1</sup>",
      relativeAtomicMass: "101.1",
      metallic: true,
      radioactivity: false,
    },
    {
      index: 76,
      chemicalymbol: "Os",
      chemicalName: "锇",
      valenceElectron: "5d<sup>6</sup>6s<sup>2</sup>",
      relativeAtomicMass: 190.2,
      metallic: true,
    },
    {
      index: 108,
      chemicalymbol: "Hs",
      chemicalName: "钅黑*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔277〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VIIIb: [
    {
      index: 27,
      chemicalymbol: "Co",
      chemicalName: "钴",
      valenceElectron: "3d<sup>7</sup>4s<sup>2</sup>",
      relativeAtomicMass: 58.93,
      metallic: true,
    },
    {
      index: 45,
      chemicalymbol: "Rh",
      chemicalName: "铑",
      valenceElectron: "4d<sup>8</sup>5s<sup>1</sup>",
      relativeAtomicMass: 102.9,
      metallic: true,
      radioactivity: false,
    },
    {
      index: 77,
      chemicalymbol: "Ir",
      chemicalName: "铱",
      valenceElectron: "5d<sup>7</sup>6s<sup>2</sup>",
      relativeAtomicMass: 192.2,
      metallic: true,
    },
    {
      index: 109,
      chemicalymbol: "Mt",
      chemicalName: "钅麦*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔268〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  VIIIc: [
    {
      index: 28,
      chemicalymbol: "Ni",
      chemicalName: "镍",
      valenceElectron: "3d<sup>8</sup>4s<sup>2</sup>",
      relativeAtomicMass: 58.69,
      metallic: true,
    },
    {
      index: 46,
      chemicalymbol: "Pd",
      chemicalName: "钯",
      valenceElectron: "4d<sup>10</sup>",
      relativeAtomicMass: 106.4,
      metallic: true,
    },
    {
      index: 78,
      chemicalymbol: "Pt",
      chemicalName: "铂",
      valenceElectron: "5d<sup>9</sup>6s<sup>1</sup>",
      relativeAtomicMass: 186.2,
      metallic: true,
    },
    {
      index: 110,
      chemicalymbol: "Ds",
      chemicalName: "钅达*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔281〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  IB: [
    {
      index: 29,
      chemicalymbol: "Cu",
      chemicalName: "铜",
      valenceElectron: "3d<sup>10</sup>4s<sup>1</sup>",
      relativeAtomicMass: 63.55,
      metallic: true,
    },
    {
      index: 47,
      chemicalymbol: "Ag",
      chemicalName: "银",
      valenceElectron: "4d<sup>10</sup>5s<sup>1</sup>",
      relativeAtomicMass: "107.9",
      metallic: true,
      radioactivity: false,
    },
    {
      index: 79,
      chemicalymbol: "Au",
      chemicalName: "金",
      valenceElectron: "5d<sup>10</sup>6s<sup>1</sup>",
      relativeAtomicMass: 197.0,
      metallic: true,
    },
    {
      index: 111,
      chemicalymbol: "Rg",
      chemicalName: "钅仑*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔272〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  IIB: [
    {
      index: 30,
      chemicalymbol: "Zn",
      chemicalName: "锌",
      valenceElectron: "3d<sup>10</sup>4s<sup>2</sup>",
      relativeAtomicMass: 65.41,
      metallic: true,
    },
    {
      index: 48,
      chemicalymbol: "Cd",
      chemicalName: "铬",
      valenceElectron: "4d<sup>10</sup>5s<sup>2</sup>",
      relativeAtomicMass: 112.4,
      metallic: true,
      radioactivity: false,
    },
    {
      index: 80,
      chemicalymbol: "Hg",
      chemicalName: "汞",
      valenceElectron: "5d<sup>10</sup>6s<sup>2</sup>",
      relativeAtomicMass: 200.6,
      metallic: true,
    },
    {
      index: 112,
      chemicalymbol: "Uub",
      chemicalName: "*",
      valenceElectron: "  ",
      relativeAtomicMass: "〔285〕",
      metallic: true,
      radioactivity: true,
    },
  ],
  IIIA: [
    {
      index: 5,
      chemicalymbol: "B",
      chemicalName: "硼",
      valenceElectron: "2s<sup>2</sup>2p<sup>1</sup>",
      relativeAtomicMass: 10.81,
      metallic: false,
    },
    {
      index: 13,
      chemicalymbol: "Al",
      chemicalName: "铝",
      valenceElectron: "3s<sup>2</sup>3p<sup>1</sup>",
      relativeAtomicMass: 26.98,
      metallic: true,
    },
    {
      index: 31,
      chemicalymbol: "Ga",
      chemicalName: "镓",
      valenceElectron: "4s<sup>2</sup>4p<sup>1</sup>",
      relativeAtomicMass: 69.72,
      metallic: true,
    },
    {
      index: 49,
      chemicalymbol: "In",
      chemicalName: "铟",
      valenceElectron: "5s<sup>2</sup>5p<sup>1</sup>",
      relativeAtomicMass: 114.8,
      metallic: true,
    },
    {
      index: 81,
      chemicalymbol: "Ti",
      chemicalName: "铊",
      valenceElectron: "6s<sup>2</sup>6p<sup>1</sup>",
      relativeAtomicMass: 114.8,
      metallic: true,
    },
    {
      blank: true,
    },
  ],
  IVA: [
    {
      index: 6,
      chemicalymbol: "C",
      chemicalName: "碳",
      valenceElectron: "2s<sup>2</sup>2p<sup>2</sup>",
      relativeAtomicMass: 12.01,
      metallic: false,
    },
    {
      index: 14,
      chemicalymbol: "Si",
      chemicalName: "硅",
      valenceElectron: "3s<sup>2</sup>3p<sup>2</sup>",
      relativeAtomicMass: 28.09,
      metallic: false,
    },
    {
      index: 32,
      chemicalymbol: "Ge",
      chemicalName: "锗",
      valenceElectron: "4s<sup>2</sup>4p<sup>2</sup>",
      relativeAtomicMass: 69.72,
      metallic: true,
    },
    {
      index: 50,
      chemicalymbol: "Sn",
      chemicalName: "锡",
      valenceElectron: "5s<sup>2</sup>5p<sup>2</sup>",
      relativeAtomicMass: 118.7,
      metallic: true,
    },
    {
      index: 82,
      chemicalymbol: "Pb",
      chemicalName: "铅",
      valenceElectron: "6s<sup>2</sup>6p<sup>2</sup>",
      relativeAtomicMass: 207.2,
      metallic: true,
    },
    {
      blank: true,
    },
  ],
  VA: [
    {
      index: 7,
      chemicalymbol: "N",
      chemicalName: "氮",
      valenceElectron: "2s<sup>2</sup>2p<sup>3</sup>",
      relativeAtomicMass: 14.01,
      metallic: false,
    },
    {
      index: 15,
      chemicalymbol: "P",
      chemicalName: "磷",
      valenceElectron: "3s<sup>2</sup>3p<sup>3</sup>",
      relativeAtomicMass: 30.97,
      metallic: false,
    },
    {
      index: 33,
      chemicalymbol: "As",
      chemicalName: "砷",
      valenceElectron: "4s<sup>2</sup>4p<sup>3</sup>",
      relativeAtomicMass: 74.92,
      metallic: false,
    },
    {
      index: 51,
      chemicalymbol: "Sb",
      chemicalName: "锑",
      valenceElectron: "5s<sup>2</sup>5p<sup>3</sup>",
      relativeAtomicMass: 121.8,
      metallic: true,
    },
    {
      index: 83,
      chemicalymbol: "Bi",
      chemicalName: "铋",
      valenceElectron: "6s<sup>2</sup>6p<sup>3</sup>",
      relativeAtomicMass: 209.0,
      metallic: true,
    },
    {
      blank: true,
    },
  ],
  VIA: [
    {
      index: 8,
      chemicalymbol: "O",
      chemicalName: "氧",
      valenceElectron: "2s<sup>2</sup>2p<sup>4</sup>",
      relativeAtomicMass: 16.0,
      metallic: false,
    },
    {
      index: 16,
      chemicalymbol: "S",
      chemicalName: "硫",
      valenceElectron: "3s<sup>2</sup>3p<sup>4</sup>",
      relativeAtomicMass: 32.06,
      metallic: false,
    },
    {
      index: 34,
      chemicalymbol: "Se",
      chemicalName: "硒",
      valenceElectron: "4s<sup>2</sup>4p<sup>4</sup>",
      relativeAtomicMass: 78.96,
      metallic: false,
    },
    {
      index: 52,
      chemicalymbol: "Te",
      chemicalName: "碲",
      valenceElectron: "5s<sup>2</sup>5p<sup>4</sup>",
      relativeAtomicMass: 127.6,
      metallic: false,
    },
    {
      index: 84,
      chemicalymbol: "Po",
      chemicalName: "钋",
      valenceElectron: "6s<sup>2</sup>6p<sup>4</sup>",
      relativeAtomicMass: "〔209.0〕",
      metallic: true,
      radioactivity: true,
    },
    {
      blank: true,
    },
  ],
  VIIA: [
    {
      index: 9,
      chemicalymbol: "F",
      chemicalName: "氟",
      valenceElectron: "2s<sup>2</sup>2p<sup>5</sup>",
      relativeAtomicMass: 19.0,
      metallic: false,
    },
    {
      index: 17,
      chemicalymbol: "Cl",
      chemicalName: "氯",
      valenceElectron: "3s<sup>2</sup>3p<sup>5</sup>",
      relativeAtomicMass: 35.45,
      metallic: false,
    },
    {
      index: 35,
      chemicalymbol: "Br",
      chemicalName: "溴",
      valenceElectron: "4s<sup>2</sup>4p<sup>5</sup>",
      relativeAtomicMass: 79.9,
      metallic: false,
    },
    {
      index: 53,
      chemicalymbol: "I",
      chemicalName: "碘",
      valenceElectron: "5s<sup>2</sup>5p<sup>5</sup>",
      relativeAtomicMass: 126.9,
      metallic: false,
    },
    {
      index: 85,
      chemicalymbol: "At",
      chemicalName: "砹",
      valenceElectron: "6s<sup>2</sup>6p<sup>5</sup>",
      relativeAtomicMass: "〔201〕",
      metallic: false,
      radioactivity: true,
    },
    {
      blank: true,
    },
  ],
  ZERO: [
    {
      index: 2,
      chemicalymbol: "He",
      chemicalName: "氦",
      valenceElectron: "1s<sup>2",
      relativeAtomicMass: 4.003,
      metallic: false,
    },
    {
      index: 10,
      chemicalymbol: "Ne",
      chemicalName: "氖",
      valenceElectron: "2s<sup>2</sup>2p<sup>6</sup>",
      relativeAtomicMass: 21.18,
      metallic: false,
    },
    {
      index: 18,
      chemicalymbol: "Ar",
      chemicalName: "氩",
      valenceElectron: "3s<sup>2</sup>3p<sup>6</sup>",
      relativeAtomicMass: 39.95,
      metallic: false,
    },
    {
      index: 36,
      chemicalymbol: "Kr",
      chemicalName: "氪",
      valenceElectron: "4s<sup>2</sup>4p<sup>6</sup>",
      relativeAtomicMass: 83.8,
      metallic: false,
    },
    {
      index: 54,
      chemicalymbol: "Xe",
      chemicalName: "氙",
      valenceElectron: "5s<sup>2</sup>5p<sup>6</sup>",
      relativeAtomicMass: 131.3,
      metallic: false,
      radioactivity: false,
    },
    {
      index: 86,
      chemicalymbol: "Rn",
      chemicalName: "氡",
      valenceElectron: "6s<sup>2</sup>6p<sup>6</sup>",
      relativeAtomicMass: "〔222〕",
      metallic: false,
      radioactivity: true,
    },
    {
      blank: true,
    },
  ],
});

function checkExcessive(key) {
  return [
    "IIIB",
    "IVB",
    "VB",
    "VIB",
    "VIIB",
    "VIIIa",
    "VIIIb",
    "VIIIc",
    "IB",
    "IIB",
  ].includes(key);
}

function borderFix(key) {
  return [2, 5, 13].includes(key);
}

function cutElectronics(index) {
  return electronics.value.slice(5 - index);
}
function cutElectronicsNum(index) {
  return electronicsNum.value.slice(5 - index);
}
</script>

<template>
  <header>

    <div class="wrapper">
      <div class="e-con">
        <div class="period-index">
          <div class="pi-des des-bg"></div>
          <div class="pi-con fdisxy" v-for="index in 7">{{index}}</div>
        </div>
        <div class="elements fdisc" v-for="clans,key in tableData" :class="[key=='VIIIa'?'special-width':'']">
          <div class="des-bg des-a fdisc" v-if="key=='IA'">
            <div class="clans-name">I<span class="text-red">A</span></div>
            <div class="r-text">1</div>
          </div>
          <div class="des-bg des-b fdisc" v-else-if="key=='IIA'">
            <div>II<span class="text-red">A</span></div>
            <div class="r-text">2</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='IIIB'">
            <div>III<span class="text-red">B</span></div>
            <div class="r-text">3</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='IVB'">
            <div>IV<span class="text-red">B</span></div>
            <div class="r-text">4</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='VB'">
            <div>V<span class="text-red">B</span></div>
            <div class="r-text">5</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='VIB'">
            <div>VI<span class="text-red">B</span></div>
            <div class="r-text">6</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='VIIB'">
            <div>VII<span class="text-red">B</span></div>
            <div class="r-text">7</div>
          </div>
          <div class="des-bg des-d fdisr" v-else-if="key=='VIIIa'" v-once>
            <div class="index-head">VIII</div>
            <div class="i-text">8</div>
            <div class="i-text">9</div>
            <div class="i-text">10</div>
          </div>
          <div v-else-if="key=='VIIIb'"></div>
          <div v-else-if="key=='VIIIc'"></div>
          <div class="des-bg des-c fdisc" v-else-if="key=='IB'">
            <div>I<span class="text-red">B</span></div>
            <div class="r-text">11</div>
          </div>
          <div class="des-bg des-c fdisc" v-else-if="key=='IIB'">
            <div>II<span class="text-red">B</span></div>
            <div class="r-text">12</div>
          </div>
          <div class="des-bg des-b fdisc bdl-normal" v-else-if="key=='IIIA'">
            <div>III<span class="text-red">A</span></div>
            <div class="r-text">13</div>
          </div>
          <div class="des-bg des-b fdisc" v-else-if="key=='IVA'">
            <div>IV<span class="text-red">A</span></div>
            <div class="r-text">14</div>
          </div>
          <div class="des-bg des-b fdisc" v-else-if="key=='VA'">
            <div>V<span class="text-red">A</span></div>
            <div class="r-text">15</div>
          </div>
          <div class="des-bg des-b fdisc" v-else-if="key=='VIA'">
            <div>VI<span class="text-red">A</span></div>
            <div class="r-text">16</div>
          </div>
          <div class="des-bg des-b fdisc" v-else-if="key=='VIIA'">
            <div>VII<span class="text-red">A</span></div>
            <div class="r-text">17</div>
          </div>
          <div class="des-bg des-a fdisc bdl-normal" v-else-if="key=='ZERO'">
            <div>0</div>
            <div class="r-text">18</div>
          </div>
          <div class="element-con fdisc" v-for="element in clans" :class="[element.metallic?'elc-metal-bg':'elc-nometal-bg',key=='IIIB'?'bdl-red':'',key=='IIB'?'bdr-red':'', checkExcessive(key)?'excessive':'',element.blank?'blank-con':'',borderFix(element.index)?'bdl-normal':'']">
            <div class="ec-a-s fdisc" v-if="element.index=='57~71'||element.index=='89~103'">
              <div class="e-index-s">{{element.index}}</div>
              <div class="e-symbol-s" :class="[element.index=='89~103'?'text-red':'']">{{element.chemicalymbol}}</div>
            </div>
            <div class="ec-a fdisr" v-else>
              <div class="e-index">{{element.index}}</div>
              <div class="e-symbol" :class="[element.radioactivity?'text-red':'']">{{element.chemicalymbol}}</div>
            </div>

            <div class="ec-b">
              {{element.chemicalName}}
            </div>
            <div class="ec-c" v-html="element.valenceElectron">

            </div>
            <div class="ec-d">
              {{element.relativeAtomicMass}}
            </div>
          </div>

        </div>
        <div class="electronic-con fdisc">
          <div class="des-e fdisxy">电子层</div>
          <div class="ecs fdisc" v-for="(symbol,index) in electronics">
            <div class="ec-item" v-for="(eleCut,cindex) in cutElectronics(index)">{{eleCut}}</div>
          </div>
        </div>
        <div class="electronic-con fdisc">
          <div class="des-e fdisxy">0族电子数</div>
          <div class="ecs fdisc" v-for="(symbol,index) in electronicsNum">
            <div class="ec-item" v-for="(eleCut,cindex) in cutElectronicsNum(index)">{{eleCut}}</div>
          </div>
        </div>
      </div>

      <div class="extra-con fdisr" style="margin-top: 50px;">
        <div class="period-index">
          <div class="extra-pi-con fdisxy">镧系</div>
        </div>
        <div class="extra-element-con fdisc" v-for="element in LaSeries" :class="[element.metallic?'elc-metal-bg':'elc-nometal-bg',]">
          <div class="ec-a-s fdisc" v-if="element.index=='57~71'||element.index=='89~103'">
            <div class="e-index-s">{{element.index}}</div>
            <div class="e-symbol-s" :class="[element.index=='89~103'?'text-red':'']">{{element.chemicalymbol}}</div>
          </div>
          <div class="ec-a fdisr" v-else>
            <div class="e-index">{{element.index}}</div>
            <div class="e-symbol" :class="[element.radioactivity?'text-red':'']">{{element.chemicalymbol}}</div>
          </div>

          <div class="ec-b">
            {{element.chemicalName}}
          </div>
          <div class="ec-c" v-html="element.valenceElectron">

          </div>
          <div class="ec-d">
            {{element.relativeAtomicMass}}
          </div>
        </div>
      </div>

      <div class="extra-con fdisr" style="margin-top: 10px;">
        <div class="period-index">
          <div class="extra-pi-con fdisxy">锕系</div>
        </div>
        <div class="extra-element-con fdisc" v-for="element in AcSeries" :class="[element.metallic?'elc-metal-bg':'elc-nometal-bg',]">
          <div class="ec-a-s fdisc" v-if="element.index=='57~71'||element.index=='89~103'">
            <div class="e-index-s">{{element.index}}</div>
            <div class="e-symbol-s" :class="[element.index=='89~103'?'text-red':'']">{{element.chemicalymbol}}</div>
          </div>
          <div class="ec-a fdisr" v-else>
            <div class="e-index">{{element.index}}</div>
            <div class="e-symbol" :class="[element.radioactivity?'text-red':'']">{{element.chemicalymbol}}</div>
          </div>

          <div class="ec-b">
            {{element.chemicalName}}
          </div>
          <div class="ec-c" v-html="element.valenceElectron">

          </div>
          <div class="ec-d">
            {{element.relativeAtomicMass}}
          </div>
        </div>
      </div>
    </div>
  </header>

</template>

<style scoped>
.e-con {
  width: auto;
  display: flex;
  flex-direction: row;
}

.elements {
  justify-content: flex-end;
  flex-wrap: wrap;
}

.element-con {
  width: 90px;
  height: 130px;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
  cursor: pointer;
}

.extra-element-con {
  width: 90px;
  height: 130px;
  border-right: 2px solid black;
  cursor: pointer;
}

.extra-element-con:last-child {
  border-right: none;
}

.elc-metal-bg {
  background-color: #c5e6b4;
}

.elc-nometal-bg {
  background-color: #54c22e;
}

.ec-a {
  align-items: center;
  width: 100%;
}
.e-index {
  font-weight: 600;
  font-size: 24px;
  color: #c2213c;
  width: 50%;
  text-align: center;
}

.e-index-s {
  font-weight: 600;
  font-size: 24px;
  color: #c2213c;
  width: 100%;
  text-align: center;
}

.e-symbol {
  font-weight: 700;
  font-size: 22px;
  width: 50%;
  text-align: center;
}

.e-symbol-s {
  font-weight: 700;
  font-size: 28px;
  width: 100%;
  text-align: center;
}

.ec-b {
  font-weight: 600;
  font-size: 20px;
  text-align: center;
}

.ec-c {
  width: 80%;
  text-align: right;
  font-size: 16px;
  font-weight: 400;
}

.ec-d {
  font-size: 18px;
  font-weight: 400;
  margin-left: 10px;
}

.period-index {
  display: flex;
  flex-direction: column;
  border: 2px sold black;
  border-top: none;
  width: auto;
  height: auto;
}

.pi-des {
  width: 60px;
  height: 45px;
  border: 2px solid black;
}

.des-bg {
  background-color: #ecf0ef;
}

.clans-name {
  width: 100%;
  height: 30px;
}

.des-a {
  height: 45px;
  border-top: 2px solid black;
  border-right: 2px solid black;
  border-bottom: 2px solid black;
  font-size: 18px;
  text-align: center;
}
.des-b {
  height: 60px;
  border-top: 2px solid black;
  border-right: 2px solid black;
  border-bottom: 2px solid black;
  font-size: 18px;
  text-align: center;
  justify-content: flex-end;
}

.des-c {
  height: 88px;
  border-top: 2px solid black;
  border-right: 2px solid black;
  font-size: 18px;
  text-align: center;
  justify-content: flex-end;
}

.des-d {
  align-items: center;
  justify-content: center;
  width: 270px;
  border-top: 2px solid black;
  border-right: 2px solid black;
  font-size: 18px;
  text-align: center;
  flex-wrap: wrap;
}

.index-head {
  width: 100%;
  height: 46px;
}

.i-text {
  width: 33%;
  height: 40px;
  line-height: 40px;
  text-align: right;
}

.pi-con {
  width: 60px;
  height: 130px;
  background-color: #ecf0ef;
  font-size: 20px;
  border-bottom: 2px solid black;
  border-left: 2px solid black;
  border-right: 2px solid black;
}

.extra-pi-con {
  width: 60px;
  height: 130px;
  background-color: #ecf0ef;
  font-size: 20px;
  border-right: 2px solid black;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}

.des-e {
  width: 60px;
  height: 45px;

  text-align: center;
  border-top: 2px solid black;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
}

.electronic-con {
  width: 60px;
}

.ecs {
  justify-content: flex-end;
  height: 130px;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
}

.ec-item {
  height: 21.6px;
  width: 100%;
  line-height: 18px;
  text-align: center;
  font-size: 16px;
  font-weight: bold;
}

.extra-con {
  border: 4px solid #b32340;
  
}

.fdisxy {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.e-height {
  height: 200px;
}

.fdisr {
  display: flex;
  flex-direction: row;
}

.fdisc {
  display: flex;
  flex-direction: column;
}

.text-red {
  font-weight: bolder;
  color: #b72035;
}

.r-text {
  width: 80%;
  height: 15px;
  line-height: 10px;
  text-align: right;
}
.bdl-red {
  border-left: 4px solid #b32340 !important;
}

.bdt-red {
  border-top: 4px solid #b32340;
}
.excessive {
}
.excessive:nth-child(2) {
  border-top: 4px solid #b32340 !important;
}

.excessive:last-child {
  border-bottom: 4px solid #b32340 !important;
}

.bdr-red {
  border-right: 4px solid #b32340 !important;
}

.bdb-red {
  border-bottom: 4px solid #b32340;
}
.bdl-normal {
  border-left: 2px solid black;
}
.special-width {
  width: 90px;
}

.blank-con {
  background-color: white !important;
  border: none !important;
}
</style>
