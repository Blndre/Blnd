blnd
# Modela sade ya bikarhênerekî di bernameya blnd.96 da
class Bikarhêner:
    def __init__(self, navê_bikarhêner):
        self.navê_bikarhêner = navê_bikarhêner
        print(f"Bikarhênerê nû '{self.navê_bikarhêner}' hate çêkirin.")

# Modela sade ya vîdyoyekê di bernameya blnd.96 da
class Vîdyo:
    def __init__(self, bikarhêner, sernivîs):
        self.bikarhêner = bikarhêner
        self.sernivîs = sernivîs
        self.hezjêkirin = 0 # Li destpêkê hejmara laykan sifre

    def nîşan_bide(self):
        # Ev fonksiyon agahiyên vîdyoyê nîşan dide
        print("---------------------------------")
        print(f"👤 Barkirî ji aliyê: @{self.bikarhêner.navê_bikarhêner}")
        print(f"📝 Sernivîs: {self.sernivîs}")
        print(f"❤️ Hezjêkirin: {self.hezjêkirin}")
        print("---------------------------------")

    def hezjêkirin_zêdeke(self):
        # Ev fonksiyon laykekê zêde dike
        self.hezjêkirin += 1
        print(f"👍 Te hezjêkirina xwe ji bo vîdyoya @{self.bikarhêner.navê_bikarhêner} da.")


# --- Destpêka Bernameya "blnd.96" ---

print("🌟 Bi xêr hatî bo bernameya blnd.96 🌟\n")

# 1. Çend bikarhêneran çêdikin
bikarhêner_1 = Bikarhêner("blnd.96")
bikarhêner_2 = Bikarhêner("hezkerê_kurdistanê")
bikarhêner_3 = Bikarhêner("paytext_duhok")
print("\n")

# 2. Bikarhêner çend vîdyoyan "bar dikin"
vîdyo_1 = Vîdyo(bikarhêner_1, "Dîmenek ji Çiyayê Garê.")
vîdyo_2 = Vîdyo(bikarhêner_2, "Silav hevalan! #kurdistan")
vîdyo_3 = Vîdyo(bikarhêner_3, "Xwarina Kurdî ya herî xweş! 😋")

# Hemî vîdyo di rûpela "Bo Te" da ne
rûpela_bo_te = [vîdyo_1, vîdyo_2, vîdyo_3]

# 3. Nîşandana vîdyoyan liser rûpela sereke
print("📺 Rûpela 'Bo Te' tê nîşandan:\n")
for v in rûpela_bo_te:
    v.nîşan_bide()

# 4. Werbigire ku bikarhêner li vîdyoya yekem temaşe dike û laykekê lê dide
print("\n... Niha bikarhênerek laykekê dide vîdyoya yekem ...\n")
vîdyo_1.hezjêkirin_zêdeke()

# 5. Vîdyoyê careka dî nîşan bide da ku bibînî layk zêde bûye
print("\nAgahiyên vîdyoyê piştî laykê:")
vîdyo_1.nîşan_bide()

// Pêdiviye pakêta bingehîn ya Flutter hebe
import 'package:flutter/material.dart';

// Ev cihê serekî ye ku bername ji wir dest pê dike
void main() {
  runApp(Blnd96App());
}

// Ev pêkhateya serekî (widget) ya bernameyê ye
class Blnd96App extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // MaterialApp bingeha bernameyê ye
    return MaterialApp(
      // Sernavê bernameyê di lista sepanan de
      title: 'blnd.96',
      
      // Rûpela malê (Home Page)
      home: Scaffold(
        // Beşê jorîn yê bernameyê (AppBar)
        appBar: AppBar(
          title: Text('blnd.96'),
          backgroundColor: Colors.blueAccent, // Rengê beşê jorîn
        ),
        
        // Beşê navendî yê bernameyê (Body)
        body: Center(
          // Hemî tiştên di hundirê vê de dê li navendê bin
          child: Text(
            'Bi xêr hatî bo cîhana blnd.96!',
            style: TextStyle(fontSize: 22), // Mezinahiya nivîsê
          ),
        ),
      ),
    );
  }
}
// Pêdiviye pakêta bingehîn ya Flutter hebe
import 'package:flutter/material.dart';

// --- PÊNGAVA 1: MODELÊN DATAYÊ ---

// Modela ji bo Endamekî Qebîlê
class Endam {
  final String nav;

  Endam({required this.nav});
}

// Modela ji bo Qebîlê bixwe
class Qebîle {
  final String nav;
  final String şirovekirin;
  final List<Endam> endam; // Listeya endamên vê qebîlê

  Qebîle({
    required this.nav,
    required this.şirovekirin,
    required this.endam,
  });
}


// --- PÊNGAVA 2: DATAYÊN MÎNAK ---

// Çend endaman çêdikin
final endam1 = Endam(nav: "blnd.96");
final endam2 = Endam(nav: "Lawkê Kurd");
final endam3 = Endam(nav: "Keça Zaxoyî");
final endam4 = Endam(nav: "Duhokî");

// Çend qebîleyan çêdikin û endaman dixin nav wan
final List<Qebîle> hemîQebîle = [
  Qebîle(
    nav: "Gamerên Kurdistanê",
    şirovekirin: "Cihê hezkiriyên lîstikên vîdyoyî.",
    endam: [endam1, endam4],
  ),
  Qebîle(
    nav: "Hezkiriyên Xwarinê",
    şirovekirin: "Em li ser xwarinên Kurdî diaxivin.",
    endam: [endam2, endam3, endam4],
  ),
  Qebîle(
    nav: "Fîlm û Sînema",
    şirovekirin: "Nîqaş li ser fîlmên nû û kevin.",
    endam: [endam1, endam2, endam3],
  ),
];


// --- PÊNGAVA 3: DESTPÊKA BERNAME Û RÛPELAN ---

void main() {
  runApp(QebîleApp());
}

// Ev pêkhateya serekî (widget) ya bernameyê ye
class QebîleApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Qebîle App',
      theme: ThemeData(
        primarySwatch: Colors.teal, // Rengê serekî yê bernameyê
      ),
      home: RûpelaSereke(), // Rûpela yekem ku vedibe
    );
  }
}

// Rûpela ku hemî qebîleyan nîşan dide
class RûpelaSereke extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Hemî Qebîle'),
      ),
      body: ListView.builder(
        itemCount: hemîQebîle.length,
        itemBuilder: (context, index) {
          final qebîle = hemîQebîle[index];
          return Card( // Em Card bikar tînin da ku ciwantir be
            margin: EdgeInsets.all(8.0),
            child: ListTile(
              leading: Icon(Icons.group_work, size: 40),
              title: Text(qebîle.nav, style: TextStyle(fontWeight: FontWeight.bold)),
              subtitle: Text(qebîle.şirovekirin),
              trailing: Icon(Icons.arrow_forward_ios),
              onTap: () {
                // Dema tu li ser qebîlê bitikînî, dê te bibe rûpela hûrguliyan
                Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => RûpelaHûrguliyan(qebîle: qebîle),
                  ),
                );
              },
            ),
          );
        },
      ),
    );
  }
}

// Rûpela ku agahiyên tenê yek qebîlê nîşan dide
class RûpelaHûrguliyan extends StatelessWidget {
  final Qebîle qebîle;

  RûpelaHûrguliyan({required this.qebîle});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(qebîle.nav), // Navê qebîlê li jor
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              qebîle.şirovekirin,
              style: TextStyle(fontSize: 18, fontStyle: FontStyle.italic, color: Colors.grey[700]),
            ),
            SizedBox(height: 20),
            Divider(), // Xêzekê lê zêde bike
            Padding(
              padding: const EdgeInsets.symmetric(vertical: 8.0),
              child: Text(
                'Endam (${qebîle.endam.length})', // Hejmara endaman nîşan bide
                style: TextStyle(fontSize: 22, fontWeight: FontWeight.bold),
              ),
            ),
            // Listeya endamên vê qebîlê nîşan bide
            Expanded(
              child: ListView.builder(
                itemCount: qebîle.endam.length,
                itemBuilder: (context, index) {
                  final endam = qebîle.endam[index];
                  return Card(
                    child: ListTile(
                      leading: Icon(Icons.person_outline),
                      title: Text(endam.nav),
                    ),
                  );
                },
              ),
            ),
          ],
        ),
      ),
    );
  }
}
