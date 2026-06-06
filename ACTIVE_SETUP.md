# Aktives Trading Setup — Stand: 6. Juni 2026

---

## Kapital-Übersicht

| | |
|---|---|
| OKX Gesamt | ~$233 USDC |
| In offenen Positionen | ~$121 USDC (Betrag) |
| FOMC Reserve (nicht anfassen) | ~$87 USDC |
| Pre-FOMC Budget noch frei | **$0 — beide Positionen offen** |

---

## Offene Positionen (Stand 06.06.2026)

| | Position 1 | Position 2 |
|---|---|---|
| Entry | ~$60,000 | ~$60,800 |
| Betrag | ~$73 USDC | ~$48 USDC |
| TP | **$63,500** | **$65,000** |
| SL | **$58,800** | **$59,200** |
| R:R | 2.9:1 ✓ | 2.6:1 ✓ |
| SL auf | Mark Price | Mark Price |

**Scaled Exit Plan (beide Positionen):**
- Bei $62,400 (2R) → 25% schließen, SL auf Breakeven ziehen
- Bei $64,000 (4R) → weitere 25% schließen
- Rest → Trailing Stop

---

## Aktive Alarme

| Level | Richtung | Aktion |
|---|---|---|
| **$62,400** | ↑ | 25% schließen → SL auf Breakeven |
| **$63,500** | ↑ | TP Position 1 (Rest) |
| **$65,000** | ↑ | TP Position 2 (Rest) |
| **$60,000** | ↓ | Risk Manager fragen — Hält Support? |
| **$59,200** | ↓ | SL Position 2 trigert |
| **$58,800** | ↓ | SL Position 1 trigert |

---

## REGELN — VERBINDLICH (vom User selbst aufgestellt)

### Pflicht vor jedem Entry
- [ ] R:R ≥ 2:1 berechnet? **Kein Trade darunter — niemals**
- [ ] SL unter strukturellem Level (Swing Low + 2% Offset)?
- [ ] 15m Candle muss Level bestätigen (close über/unter)
- [ ] Volumen über 20er Durchschnitt?
- [ ] Katalysator definiert? Kein Entry aus Gefühl
- [ ] Max 2% Kapital-Risiko pro Trade = max $4.66 Verlust

### Festgelegte Limits
| Regel | Wert |
|---|---|
| Max Verlust gesamt | 20% des Kapitals = $46.60 |
| Max Risiko pro Trade | **2% = $4.66** |
| Min R:R | **2:1** — Ziel: 3:1 |
| SL Abstand von Support | min 2% Offset |
| Kein Nachkauf | in offene Leverage-Position |
| Invalidierung BTC | unter $55,000 |
| 2 Verluste hintereinander | **STOP — Circuit Breaker** |

### R:R Ziele nach Style
| Style | Min R:R | Ziel |
|---|---|---|
| Scalp | 1.5:1 | 2:1 |
| Day Trade | 2:1 | **3:1** ← unser Standard |
| Swing | 3:1 | 5:1 |

---

## OKX Sizing — Exakte Formeln

```
Betrag-Feld = POSITIONSGRÖSSE (NICHT Margin!)
Bei 3x: Margin × 3 = Betrag-Feld

Schritt 1: Max Risikobetrag
  Risk$ = Kapital × 0.02 = $233 × 0.02 = $4.66

Schritt 2: SL-Distanz
  SL% = |Entry - SL| / Entry × 100

Schritt 3: Positionsgröße
  Position$ = Risk$ / SL-Distanz%

Schritt 4: OKX Eingaben
  Betrag-Feld = Position$ (USDC)
  TP% = TP-Distanz% × Hebel (= % der Margin)
  SL% = SL-Distanz% × Hebel (= % der Margin)
  SL immer auf: Mark Price (nicht Last Price)

Beispiel:
  Entry $60,000 | SL $58,500 | TP $63,000
  SL-Distanz = 2.5% | R:R = 5%/2.5% = 2:1
  Position$ = $4.66 / 0.025 = $186 USDC
  TP% = 5% × 3 = 15% | SL% = 2.5% × 3 = 7.5%
```

### Sizing-Tabelle ($233 Kapital, 3x, 2% Risiko)
| SL-Distanz | Betrag-Feld | Margin | TP% bei 2:1 |
|---|---|---|---|
| 1% | $466 | $155 | 6% |
| 2% | $233 | $78 | 12% |
| 2.5% | $186 | $62 | 15% |
| 3% | $155 | $52 | 18% |
| 5% | $93 | $31 | 30% |

---

## Scaled Exit System

| Tranche | Wann | Aktion | Danach |
|---|---|---|---|
| 25% | bei 2R | Schließen | SL auf Breakeven → kein Risiko mehr |
| 25% | bei 4R | Schließen | Trailing Stop |
| 50% | bei 6R+ | Trailing | Moonbag, läuft bis Trail trifft |

**Regel:** Nach Tranche 1 → Trade ist risikofrei. Nie mehr der volle Verlust möglich.

---

## FOMC Setup (16–17 Juni 2026)

- Reserve: ~$87 USDC (reduziert durch offene Positionen)
- Strategie: Nach Fed-Entscheidung warten, nicht davor
- Ziel-Betrag: Max 2% Risiko auf FOMC-Trade
- Warum kein Zins-Cut: 89% Wahrscheinlichkeit unchanged — Powell-Sprache ist der Katalysator
- Signal abwarten: Erste 15m-Candle nach Statement schließt → Richtung bestimmt Entry

---

## Marktbild (Stand 06.06.2026)

| Indikator | Wert | Signal |
|---|---|---|
| BTC Preis | ~$60,469 | -0.92% |
| Funding Rate | -0.01219% | Negativ → Short-Crowd überhitzt, bullisch |
| 24h Tief | $59,030 | Zweimal gehalten |
| 24h Hoch | $62,648 | |
| RSI Daily | ~22-23 | Extrem überverkauft |
| Fear & Greed | 11 | Extreme Fear → konträr bullisch |
| ETF Abflüsse | 13 Tage, $4.4 Mrd | Bearisches Makrosignal |
| Polymarket <$50k | 65% | Bearischer Konsens |
| Übergeordneter Trend | Downtrend | Kein Long-Swing ohne Katalysator |

**Liquidation Cluster (Heatmap):**
- $66,500: $168M Short-Cluster → Short Squeeze Potential
- $79,650: $742M Short-Cluster → Großes Ziel wenn Squeeze startet

---

## Circuit Breaker — Auto-Stop

Bei diesen Bedingungen: **sofort aufhören, Positionen prüfen:**
- 2 Verlust-Trades hintereinander
- Tagesverlust > $10 USDC
- Marktweite Liquidationen > $100M
- NDQ fällt > 2% an einem Tag

**Psychologie-Protokoll:**
Wenn FOMO spürbar: *"Was hat sich an den Fakten geändert?"*
Wenn keine Fakten geändert: Plan bleibt. Keine Diskussion.

---

## Trade-Historie

| # | Datum | Setup | Entry | Exit | Ergebnis |
|---|---|---|---|---|---|
| 1 | 05.06 | Long 3x | $61,100 | $60,087 (SL) | **-$3.24** |
| 2 | 05.06 | Long Limit | $60,000 | offen | TP $63,500 |
| 3 | 06.06 | Long Limit | $60,800 | offen | TP $65,000 |

**Lernpunkte:**
1. Betrag-Feld = Positionsgröße (nicht Margin)
2. SL muss chartbasiert sein, nicht Bauchgefühl
3. Circuit Breaker respektiert: $267M Liquidationen → kein Entry
4. Preis-Format OKX: Komma als Tausender-Trenner (61,000 nicht 61.000)
5. R:R immer ≥ 2:1 — darunter kein Trade

---

## Optimal Setup Check — Prompt Template

Wenn Alarm triggert, diesen Prompt verwenden:

```
RISK MANAGER — SETUP CHECK

Chart: [Screenshot]
Zeitrahmen: [z.B. 15m Entry, 4H Trend]
Preis: $[X] | Muster: [Double Bottom / Support Retest / Higher Low]

Entry: $[X] | SL: $[X] (unter [Swing Low]) | TP: $[X]
R:R (selbst berechnet): [X]:1

Bestätigung:
- RSI: [Wert]
- Volumen: [über/unter 20er MA]
- MA5/10/20: [Preis darüber/darunter]
- Funding Rate: [%]
- Nächster Widerstand bis TP: $[X]

Kapital verfügbar: $[X] | Geplanter Betrag: $[X]
```

---

*Nächstes Update: FOMC 16–17 Juni 2026*
