# XAUUSD Signals — Android source project (prototype)

A native Kotlin Android app prototype for manual XAUUSD signal analysis. It fetches OHLC candles from Twelve Data's `time_series` API and calculates an experimental EMA/RSI/breakout/ATR setup. It does not connect to Exness, read MT5 mobile data, or place trades.

## Requirements
- Android Studio (current stable) with Android SDK 35.
- A Twelve Data API key. Provider availability for `XAU/USD`, intraday intervals, and historical candle depth depends on the account plan and current provider rules.
- Internet connection on the phone.

## Build and install
1. Unzip the project.
2. Open the `xauusd_android_app` folder in Android Studio.
3. Let Gradle sync and install any requested Android SDK components.
4. Connect your Android phone with USB debugging enabled, or use Build > Build Bundle(s) / APK(s) > Build APK(s).
5. Install the resulting debug APK on your phone.
6. Open the app, enter your Twelve Data API key, keep symbol as `XAU/USD` unless your provider documents another format, choose M1/M5/M15, and tap Fetch.

## Important limitations
- This is source code, not a compiled/signed APK.
- The data provider may not offer XAU/USD intraday candles on a free plan; the app reports provider errors instead of fabricating a signal.
- Provider prices and candle timing can differ from Exness. Always compare against Exness before any manual trade.
- This prototype does not yet implement background push notifications, multi-timeframe confirmation, a true tick/spread model, or robust out-of-sample backtesting. The selected timeframe is analyzed independently; the UI's M15 option is not a higher-timeframe filter for M1/M5.
- Strategy thresholds are unvalidated examples. A backtest or signal is not evidence of profitability. Demo-test before considering live use.
- The API key is stored in app-private preferences on the device, but this prototype does not encrypt it. Do not use your Exness password here.
