# Design System - Depression Control App (DCA)

## Spis treści
1. [Paleta kolorów](#paleta-kolorów)
2. [Typografia](#typografia)
3. [Komponenty](#komponenty)
4. [Layouty](#layouty)
5. [Efekty wizualne](#efekty-wizualne)
6. [Zasoby graficzne](#zasoby-graficzne)
7. [Przykłady implementacji](#przykłady-implementacji)

---

## Paleta kolorów

### Kolory podstawowe

#### Główny kolor tła (Light Blue)
- **Hex**: `#E5F2FB`
- **Zastosowanie**: Tło główne aplikacji, tło komponentów (dymki, przyciski, kafelki, drawer)
- **Użycie**: `backgroundColor: "#E5F2FB"`

#### Główny kolor tekstu (Dark Blue-Gray)
- **Hex**: `#1C2B39`
- **Zastosowanie**: Tekst główny, nagłówki, etykiety przycisków, tekst w dymkach
- **Użycie**: `color: "#1C2B39"`

#### Akcent pomarańczowy (Orange)
- **Hex**: `#E78D3D`
- **Zastosowanie**: Tekst z liczbą monet, elementy akcentujące
- **Użycie**: `color: "#E78D3D"`

#### Biały (White)
- **Hex**: `#ffffff` lub `#fff`
- **Zastosowanie**: Tło ekranów, tło rozwijanych sekcji w kafelkach
- **Użycie**: `backgroundColor: "#fff"` lub `backgroundColor: "#ffffff"`

#### Tekst wtórny (Gray)
- **Hex**: `#555`
- **Zastosowanie**: Tekst szczegółów, tekst pomocniczy
- **Użycie**: `color: "#555"`

### Podsumowanie palety

| Kolor | Hex | Zastosowanie |
|-------|-----|--------------|
| Light Blue | `#E5F2FB` | Tło główne, komponenty |
| Dark Blue-Gray | `#1C2B39` | Tekst główny, nagłówki |
| Orange | `#E78D3D` | Akcenty (monety) |
| White | `#fff` / `#ffffff` | Tło ekranów |
| Gray | `#555` | Tekst wtórny |

---

## Typografia

### Rozmiary czcionek

#### Nagłówki główne
- **Rozmiar**: `24px`
- **Waga**: `700` (bold)
- **Kolor**: `#1C2B39`
- **Zastosowanie**: Nagłówki sekcji (np. "Menu", "Wydarzenia")

```javascript
fontSize: 24,
fontWeight: "700",
color: "#1C2B39"
```

#### Tekst główny
- **Rozmiar**: `20px`
- **Waga**: `600` (semi-bold)
- **Kolor**: `#1C2B39`
- **Zastosowanie**: Tekst w dymkach, główny tekst ekranu

```javascript
fontSize: 20,
fontWeight: "600",
color: "#1C2B39"
```

#### Tekst monet
- **Rozmiar**: `20px`
- **Waga**: `700` (bold)
- **Kolor**: `#E78D3D`
- **Zastosowanie**: Wyświetlanie liczby monet

```javascript
fontSize: 20,
fontWeight: "700",
color: "#E78D3D"
```

#### Tekst menu
- **Rozmiar**: `18px`
- **Waga**: `600` (semi-bold)
- **Kolor**: `#1C2B39`
- **Zastosowanie**: Elementy menu boczne

```javascript
fontSize: 18,
fontWeight: "600",
color: "#1C2B39"
```

#### Tekst przycisków
- **Rozmiar**: `16px`
- **Waga**: `600` (semi-bold)
- **Kolor**: `#1C2B39`
- **Zastosowanie**: Etykiety przycisków akcji

```javascript
fontSize: 16,
fontWeight: "600",
color: "#1C2B39"
```

#### Tekst kafelków
- **Rozmiar**: `12px`
- **Waga**: `700` (bold)
- **Kolor**: `#1C2B39`
- **Zastosowanie**: Tytuły kuponów w kafelkach

```javascript
fontSize: 12,
fontWeight: "700",
color: "#1C2B39"
```

#### Tekst szczegółów
- **Rozmiar**: `12px`
- **Waga**: normal (domyślnie)
- **Kolor**: `#555`
- **Zastosowanie**: Szczegóły w rozwijanych sekcjach

```javascript
fontSize: 12,
color: "#555",
lineHeight: width * 0.05
```

### Podsumowanie typografii

| Element | Rozmiar | Waga | Kolor |
|---------|---------|------|-------|
| Nagłówek główny | 24px | 700 | #1C2B39 |
| Tekst główny | 20px | 600 | #1C2B39 |
| Tekst monet | 20px | 700 | #E78D3D |
| Tekst menu | 18px | 600 | #1C2B39 |
| Tekst przycisków | 16px | 600 | #1C2B39 |
| Tekst kafelków | 12px | 700 | #1C2B39 |
| Tekst szczegółów | 12px | normal | #555 |

---

## Komponenty

### Top Bar (Górny pasek)

**Lokalizacja**: Główny ekran (`app/index.tsx`)

**Struktura**:
- Kontener flexbox z `space-between`
- Menu ikona po lewej
- Pasek monet po prawej

**Style**:
```javascript
topBar: {
    flexDirection: "row",
    justifyContent: "space-between",
    alignItems: "center",
    width: "90%",
    marginBottom: 20,
}
```

**Menu Icon**:
```javascript
menuIcon: {
    padding: 10,
}
iconSmall: {
    width: 34,
    height: 24,
}
```

**Coins Bar**:
```javascript
coinsBar: {
    flexDirection: "row",
    alignItems: "center",
}
coinIconSmall: {
    width: 40,
    height: 40,
    marginRight: 1,
}
coinText: {
    fontSize: 20,
    fontWeight: "700",
    color: "#E78D3D",
}
```

---

### Speech Bubble (Dymek)

**Lokalizacja**: Główny ekran (`app/index.tsx`)

**Wizualizacja**:
- Zaokrąglony prostokąt z tłem jasnoniebieskim
- Tekst wyśrodkowany

**Style**:
```javascript
speechBubble: {
    backgroundColor: "#E5F2FB",
    borderRadius: 20,
    padding: 16,
    marginBottom: 12,
    maxWidth: "80%",
}
speechText: {
    fontSize: 20,
    textAlign: "center",
    color: "#1C2B39",
    fontWeight: "600",
}
```

---

### Monster Image (Obraz stworka)

**Lokalizacja**: Główny ekran (`app/index.tsx`)

**Wizualizacja**:
- Duży obraz z cieniem
- Zaokrąglone rogi i cień dla głębi

**Style**:
```javascript
monster: {
    width: 400,
    height: 400,
    marginVertical: 12,
    ...Platform.select({
        web: {
            boxShadow: "0 6px 10px rgba(0, 0, 0, 0.37)",
        },
        default: {
            shadowColor: "#000",
            shadowOffset: {width: 0, height: 6},
            shadowOpacity: 0.37,
            shadowRadius: 10,
            elevation: 8,
        },
    }),
}
```

**Parametry cienia**:
- **Web**: `boxShadow: "0 6px 10px rgba(0, 0, 0, 0.37)"`
- **Mobile**: `shadowOpacity: 0.37`, `shadowRadius: 10`, `elevation: 8`

---

### Buttons Row (Rząd przycisków)

**Lokalizacja**: Główny ekran (`app/index.tsx`)

**Struktura**:
- Trzy przyciski w jednym rzędzie
- Równa szerokość z marginesami

**Style**:
```javascript
buttonsRow: {
    flexDirection: "row",
    justifyContent: "space-between",
    width: "90%",
    marginTop: 10,
}
button: {
    alignItems: "center",
    backgroundColor: "#E5F2FB",
    borderRadius: 16,
    padding: 16,
    flex: 1,
    marginHorizontal: 5,
}
buttonText: {
    fontSize: 16,
    fontWeight: "600",
    color: "#1C2B39",
}
```

---

### Coupon Tiles (Kafelki kuponów)

**Lokalizacja**: Ekran kuponów (`app/coupons.tsx`)

**Struktura**:
- Siatka 2 kolumny
- Rozwijane kafelki z animacją

**Style kontenera**:
```javascript
container: {
    flex: 1,
    padding: width * 0.04, // 4% szerokości ekranu
    backgroundColor: "#fff",
}
row: {
    justifyContent: "space-between",
}
```

**Style kafelka**:
```javascript
tile: {
    width: width * 0.44, // 44% szerokości ekranu
    margin: width * 0.01, // 1% marginesu
    backgroundColor: "#E5F2FB",
    borderRadius: 16,
    overflow: "hidden",
    ...Platform.select({
        web: {
            boxShadow: "0 2px 6px rgba(0, 0, 0, 0.1)",
        },
        default: {
            shadowColor: "#000",
            shadowOpacity: 0.1,
            shadowRadius: 6,
            elevation: 3,
        },
    }),
    alignSelf: 'flex-start',
}
```

**Parametry cienia kafelków**:
- **Web**: `boxShadow: "0 2px 6px rgba(0, 0, 0, 0.1)"`
- **Mobile**: `shadowOpacity: 0.1`, `shadowRadius: 6`, `elevation: 3`

**Style przycisku kafelka**:
```javascript
tileButton: {
    paddingVertical: width * 0.005,
    alignItems: "center",
    justifyContent: "center",
}
tileTitle: {
    fontSize: 12,
    fontWeight: "700",
    color: "#1C2B39",
}
```

**Rozwijana sekcja**:
```javascript
dropdown: {
    overflow: "hidden",
    backgroundColor: "#fff",
    paddingHorizontal: width * 0.04,
}
details: {
    fontSize: 12,
    color: "#555",
    lineHeight: width * 0.05,
    marginTop: 8,
}
```

**Animacja rozwijania**:
- Czas trwania: `300ms`
- Wysokość docelowa: `180px`
- Używa `Animated.Value` i `Animated.timing`

---

### Drawer (Menu boczne)

**Lokalizacja**: `components/DrawerContent.tsx`

**Konfiguracja nawigacji** (`app/_layout.tsx`):
```javascript
screenOptions={{
    headerShown: false,
    drawerPosition: "left",
    drawerType: "slide",
    swipeEnabled: true,
    gestureEnabled: true,
    edgeWidth: 30,
    minSwipeDistance: 20,
}}
```

**Style kontenera**:
```javascript
container: {
    flex: 1,
    backgroundColor: "#E5F2FB",
}
```

**Style nagłówka**:
```javascript
header: {
    padding: 20,
    borderBottomWidth: 1,
    borderBottomColor: "#1C2B39",
}
headerText: {
    fontSize: 24,
    fontWeight: "700",
    color: "#1C2B39",
}
```

**Style elementów menu**:
```javascript
menuList: {
    flex: 1,
    paddingTop: 10,
}
menuItem: {
    padding: 16,
    borderBottomWidth: 1,
    borderBottomColor: "#1C2B39",
}
menuItemText: {
    fontSize: 18,
    fontWeight: "600",
    color: "#1C2B39",
}
```

---

### Events Panel (Panel wydarzeń)

**Lokalizacja**: `components/EventsPanel.tsx`

**Style**:
```javascript
container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
}
title: {
    fontSize: 24,
    fontWeight: '700',
    color: '#1C2B39',
}
```

---

## Layouty

### Główny ekran (Home Screen)

**Struktura**:
```
ImageBackground (tło)
├── TopBar
│   ├── MenuIcon (lewo)
│   └── CoinsBar (prawo)
├── SpeechBubble (dymek)
├── Monster Image (stworek)
└── ButtonsRow
    ├── Button 1
    ├── Button 2
    └── Button 3
```

**Style kontenera**:
```javascript
container: {
    flex: 1,
    alignItems: "center",
    paddingTop: 30,
}
```

**Tło**: `background (Custom).png`

---

### Ekran kuponów (Coupons Screen)

**Struktura**:
```
View (container)
└── FlatList (numColumns: 2)
    ├── CouponTile 1
    ├── CouponTile 2
    ├── CouponTile 3
    └── CouponTile 4
```

**Parametry siatki**:
- Liczba kolumn: `2`
- Szerokość kafelka: `44%` szerokości ekranu
- Margines między kafelkami: `1%` szerokości ekranu
- Padding kontenera: `4%` szerokości ekranu

---

### Ekran wydarzeń (Events Screen)

**Struktura**:
```
View (container)
└── EventsPanel
    └── Text (tytuł)
```

**Layout**: Wyśrodkowany, prosty panel z tytułem

---

## Efekty wizualne

### Border Radius (Zaokrąglenia)

| Komponent | Border Radius | Zastosowanie |
|-----------|---------------|--------------|
| Speech Bubble | `20px` | Dymek z tekstem |
| Buttons | `16px` | Przyciski akcji |
| Tiles | `16px` | Kafelki kuponów |

### Cienie (Shadows)

#### Cień dla obrazu stworka
**Web**:
```javascript
boxShadow: "0 6px 10px rgba(0, 0, 0, 0.37)"
```

**Mobile (iOS/Android)**:
```javascript
shadowColor: "#000",
shadowOffset: {width: 0, height: 6},
shadowOpacity: 0.37,
shadowRadius: 10,
elevation: 8,
```

#### Cień dla kafelków kuponów
**Web**:
```javascript
boxShadow: "0 2px 6px rgba(0, 0, 0, 0.1)"
```

**Mobile (iOS/Android)**:
```javascript
shadowColor: "#000",
shadowOpacity: 0.1,
shadowRadius: 6,
elevation: 3,
```

### Animacje

#### Rozwijanie kafelków kuponów
```javascript
Animated.timing(animatedHeight, {
    toValue: 180, // wysokość w px
    duration: 300, // czas w ms
    useNativeDriver: false,
})
```

**Parametry**:
- Czas trwania: `300ms`
- Wysokość docelowa: `180px`
- Używa `Animated.Value` dla płynnej animacji

### Responsywność

**Jednostki względne**:
- Szerokość kafelków: `width * 0.44` (44% szerokości ekranu)
- Padding: `width * 0.04` (4% szerokości ekranu)
- Margines: `width * 0.01` (1% szerokości ekranu)
- Line height: `width * 0.05` (5% szerokości ekranu)

**Platform-specific**:
- Użycie `Platform.select()` dla różnych stylów cieni (web vs mobile)
- Różne implementacje cieni dla iOS/Android i Web

---

## Zasoby graficzne

### Obrazy tła
- **`background (Custom).png`** - Tło głównego ekranu (ImageBackground)

### Ikony
- **`menu.png`** - Ikona menu (34x24px)
- **`coin.png`** - Ikona monet (40x40px)

### Ilustracje
- **`stworek.png`** - Główna ilustracja stworka (400x400px)

### Ikony aplikacji
- **`icon.png`** - Ikona aplikacji
- **`adaptive-icon.png`** - Ikona adaptacyjna dla Android
- **`favicon.png`** - Favicon dla web
- **`splash-icon.png`** - Ikona splash screen

### Zastosowanie obrazów

| Obraz | Rozmiar | Zastosowanie | Lokalizacja |
|-------|---------|--------------|-------------|
| `background (Custom).png` | Pełny ekran | Tło głównego ekranu | `app/index.tsx` |
| `menu.png` | 34x24px | Ikona menu | `app/index.tsx` |
| `coin.png` | 40x40px | Ikona monet | `app/index.tsx` |
| `stworek.png` | 400x400px | Ilustracja stworka | `app/index.tsx` |

---

## Przykłady implementacji

### Kompletny przykład: TopBar

```javascript
import { View, Text, Image, StyleSheet, TouchableOpacity } from "react-native";

const TopBar = () => {
    return (
        <View style={styles.topBar}>
            <TouchableOpacity style={styles.menuIcon}>
                <Image source={require("../assets/images/menu.png")} style={styles.iconSmall}/>
            </TouchableOpacity>
            <TouchableOpacity style={styles.coinsBar}>
                <Image source={require("../assets/images/coin.png")} style={styles.coinIconSmall}/>
                <Text style={styles.coinText}>1 250</Text>
            </TouchableOpacity>
        </View>
    );
};

const styles = StyleSheet.create({
    topBar: {
        flexDirection: "row",
        justifyContent: "space-between",
        alignItems: "center",
        width: "90%",
        marginBottom: 20,
    },
    menuIcon: {
        padding: 10,
    },
    iconSmall: {
        width: 34,
        height: 24,
    },
    coinsBar: {
        flexDirection: "row",
        alignItems: "center",
    },
    coinIconSmall: {
        width: 40,
        height: 40,
        marginRight: 1,
    },
    coinText: {
        fontSize: 20,
        fontWeight: "700",
        color: "#E78D3D",
    },
});
```

### Kompletny przykład: Speech Bubble

```javascript
import { View, Text, StyleSheet } from "react-native";

const SpeechBubble = ({ text }) => {
    return (
        <View style={styles.speechBubble}>
            <Text style={styles.speechText}>{text}</Text>
        </View>
    );
};

const styles = StyleSheet.create({
    speechBubble: {
        backgroundColor: "#E5F2FB",
        borderRadius: 20,
        padding: 16,
        marginBottom: 12,
        maxWidth: "80%",
    },
    speechText: {
        fontSize: 20,
        textAlign: "center",
        color: "#1C2B39",
        fontWeight: "600",
    },
});
```

### Kompletny przykład: Button

```javascript
import { TouchableOpacity, Text, StyleSheet } from "react-native";

const Button = ({ label, onPress }) => {
    return (
        <TouchableOpacity style={styles.button} onPress={onPress}>
            <Text style={styles.buttonText}>{label}</Text>
        </TouchableOpacity>
    );
};

const styles = StyleSheet.create({
    button: {
        alignItems: "center",
        backgroundColor: "#E5F2FB",
        borderRadius: 16,
        padding: 16,
        flex: 1,
        marginHorizontal: 5,
    },
    buttonText: {
        fontSize: 16,
        fontWeight: "600",
        color: "#1C2B39",
    },
});
```

### Kompletny przykład: Coupon Tile

```javascript
import { View, Text, TouchableOpacity, StyleSheet, Animated, Dimensions, Platform } from "react-native";

const { width } = Dimensions.get("window");

const CouponTile = ({ item }) => {
    const [expanded, setExpanded] = useState(false);
    const animatedHeight = useRef(new Animated.Value(0)).current;

    const toggleExpand = () => {
        if (expanded) {
            Animated.timing(animatedHeight, {
                toValue: 0,
                duration: 300,
                useNativeDriver: false,
            }).start(() => setExpanded(false));
        } else {
            setExpanded(true);
            Animated.timing(animatedHeight, {
                toValue: 180,
                duration: 300,
                useNativeDriver: false,
            }).start();
        }
    };

    return (
        <View style={styles.tile}>
            <TouchableOpacity onPress={toggleExpand} style={styles.tileButton}>
                <Text style={styles.tileTitle}>{item.title}</Text>
            </TouchableOpacity>
            <Animated.View style={[styles.dropdown, { height: animatedHeight }]}>
                {expanded && (
                    <Text style={styles.details}>{item.details}</Text>
                )}
            </Animated.View>
        </View>
    );
};

const styles = StyleSheet.create({
    tile: {
        width: width * 0.44,
        margin: width * 0.01,
        backgroundColor: "#E5F2FB",
        borderRadius: 16,
        overflow: "hidden",
        ...Platform.select({
            web: {
                boxShadow: "0 2px 6px rgba(0, 0, 0, 0.1)",
            },
            default: {
                shadowColor: "#000",
                shadowOpacity: 0.1,
                shadowRadius: 6,
                elevation: 3,
            },
        }),
        alignSelf: 'flex-start',
    },
    tileButton: {
        paddingVertical: width * 0.005,
        alignItems: "center",
        justifyContent: "center",
    },
    tileTitle: {
        fontSize: 12,
        fontWeight: "700",
        color: "#1C2B39",
    },
    dropdown: {
        overflow: "hidden",
        backgroundColor: "#fff",
        paddingHorizontal: width * 0.04,
    },
    details: {
        fontSize: 12,
        color: "#555",
        lineHeight: width * 0.05,
        marginTop: 8,
    },
});
```

---

## Zasady projektowania

### Spójność wizualna
- Wszystkie komponenty używają tej samej palety kolorów
- Jednolite zaokrąglenia (16px dla większości, 20px dla dymków)
- Spójna typografia z jasno zdefiniowanymi rozmiarami

### Responsywność
- Użycie jednostek względnych (`width * 0.XX`) dla elastyczności
- Platform-specific styles dla cieni i efektów
- FlatList z `numColumns` dla adaptacyjnych siatek

### Hierarchia wizualna
- Największe elementy: nagłówki (24px)
- Średnie elementy: tekst główny (20px), przyciski (16px)
- Najmniejsze elementy: kafelki (12px)

### Interaktywność
- Animacje dla rozwijanych sekcji (300ms)
- TouchableOpacity dla wszystkich elementów klikalnych
- Drawer z gestami (swipe, edgeWidth: 30)

---

## Notatki dla deweloperów

### Wymagane importy
```javascript
import { View, Text, Image, StyleSheet, TouchableOpacity, ImageBackground, Platform, Animated, Dimensions } from "react-native";
```

### Wymagane zależności
- `react-native-gesture-handler` - dla drawer nawigacji
- `@react-navigation/drawer` - dla menu bocznego
- `expo-router` - dla routingu

### Best Practices
1. Zawsze używaj `Platform.select()` dla platform-specific styles
2. Używaj jednostek względnych dla responsywności
3. Zachowaj spójność kolorów - używaj zmiennych lub stałych
4. Testuj animacje na różnych urządzeniach
5. Upewnij się, że cienie działają poprawnie na wszystkich platformach

---

**Ostatnia aktualizacja**: Dokumentacja stworzona na podstawie analizy kodu źródłowego aplikacji DCA

