# lllJ 设置界面标签 + 变量对照表

> 生成时间：2026-07-12 13:44 UTC
> 来源：`uitexts.toml` + `help_opt.txt`（simple_crypt 解码）+ `option_*_jp.pbd` 绑定

## Tab 一览

| Tab | 日文名 | PBD | uitexts 段 |
|-----|--------|-----|------------|
| 0 | 簡易設定 | `option_01_jp.pbd` | `screen.option_0simple` |
| 1 | 画像表示 | `option_02_jp.pbd` | `screen.option_1display` |
| 2 | ゲーム進行１ | `option_03_jp.pbd` | `screen.option_2game1` |
| 3 | ゲーム進行２ | `option_04_jp.pbd` | `screen.option_3game2` |
| 4 | テキスト | `option_05_jp.pbd` | `screen.option_4text` |
| 5 | サウンド | `option_06_jp.pbd` | `screen.option_5sound1` |
| 6 | ダイアログ | `option_07_jp.pbd` | `screen.option_6dialog` |
| 7 | マウス | `option_08_jp.pbd` | `screen.option_7mouse` |
| 8 | キーボード | `option_09_jp.pbd` | `screen.option_8keyboard1` |
| 9 | ゲームパッド | `option_10_jp.pbd` | `screen.option_9gamepad` |

## 全局按钮

| 控件 | 日文标签 | PBD 层 | 命令 |
|------|----------|--------|------|
| `reset` | 初期設定に戻す | `t_reset` | `reset` |
| `title` | タイトル画面に戻る | `t_title` | `SystemAction._title()` |
| `back` | ゲーム画面に戻る | `t_revert` | `option.close` |

## Tab 0：簡易設定

- PBD：`option_01_jp.pbd`
- help：`簡易設定`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | 画面サイズ | `-` | `-` |
| `label_b` | label | 画面切り替え | `-` | `-` |
| `label_c` | label | テキスト速度 | `-` | `-` |
| `label_d` | label | オート速度 | `-` | `-` |
| `label_e` | label | 未読スキップ | `-` | `-` |
| `label_f` | label | マスターボリューム | `-` | `-` |
| `label_g` | label | ＢＧＭ音量 | `-` | `-` |
| `label_h` | label | ＳＥ音量 | `-` | `-` |
| `label_i` | label | ボイス音量 | `-` | `-` |
| `label_j` | label | ムービー | `-` | `-` |
| `autospeed` | slider | オート速度 | `autoModeChWait` | `onSpeedSliderChange` |
| `bgm` | slider | ＢＧＭ | `bgm.volume` | `onAudioVolumeChange; setAudioOnOff/bgm/0; setAudioOnOff/bgm/1` |
| `fullscreen` | bool | 画面サイズ | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `fullscreen_off` | rad | ウインドウ | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `fullscreen_on` | rad | フルスクリーン | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `movie` | slider | ムービー | `movie.volume` | `onAudioVolumeChange; setAudioOnOff/movie/0; setAudioOnOff/movie/1` |
| `mvaudiosample_chk` | check | 音量サンプル再生 | `movieAudioSample` | `selectBasicOptionValue/mvaudiosample; setBasicOptionValue/mvaudiosample/off; setBasicOptionValue/mvaudiosample/on` |
| `se` | slider | ＳＥ音量 | `se.volume` | `onAudioVolumeChange; setAudioOnOff/se/0; setAudioOnOff/se/1` |
| `skipall` | bool | 未読スキップ | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `skipall_off` | rad | 既読のみ | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `skipall_on` | rad | すべて | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `sqscr` | bool | 画面切り替え | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `sqscr_off` | rad | １６：９ | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `sqscr_on` | rad | ４：３ | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `textspeed` | slider | テキスト速度 | `userChSpeed` | `onSpeedSliderChange` |
| `voice` | slider | ボイス音量 | `voice.volume` | `onAudioVolumeChange; setAudioOnOff/voice/0; setAudioOnOff/voice/1` |
| `wave` | slider | マスターボリューム | `waveVolume` | `onAudioVolumeChange; setAudioOnOff/wave/0; setAudioOnOff/wave/1` |

## Tab 1：画像表示

- PBD：`option_02_jp.pbd`
- help：`画面設定`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | 画面サイズ | `-` | `-` |
| `label_b` | label | 画面切り替え | `-` | `-` |
| `label_c` | label | 画面効果 | `-` | `-` |
| `label_d` | label | アニメーション効果 | `-` | `-` |
| `label_e` | label | ＥＳＣ機能 | `-` | `-` |
| `label_f` | label | スクランブル機能の選択 | `-` | `-` |
| `label_g` | label | ゲーム画面を常に手前に表示 | `-` | `-` |
| `label_h` | label | 画面アイテムの表示 | `-` | `-` |
| `label_i` | label | チャプター表示 | `-` | `-` |
| `label_j` | label | 曲名表示 | `-` | `-` |
| `label_k` | label | 話者の表情を表示 | `-` | `-` |
| `label_l` | label | ポップアップ表示 | `-` | `-` |
| `esccancel_off` | rad | スクランブル機能 | `-` | `selectBasicOptionValue/esccancel; setBasicOptionValue/esccancel/off; setBasicOptionValue/esccancel/on` |
| `esccancel_on` | rad | 右クリック | `-` | `selectBasicOptionValue/esccancel; setBasicOptionValue/esccancel/off; setBasicOptionValue/esccancel/on` |
| `facemode_off` | rad | ＯＦＦ | `faceMode` | `selectBasicOptionValue/facemode; setBasicOptionValue/facemode/off; setBasicOptionValue/facemode/on` |
| `facemode_on` | rad | ＯＮ | `faceMode` | `selectBasicOptionValue/facemode; setBasicOptionValue/facemode/off; setBasicOptionValue/facemode/on` |
| `fullscreen` | bool | 画面サイズ | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `fullscreen_off` | rad | ウインドウ | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `fullscreen_on` | rad | フルスクリーン | `fullscreen` | `selectBasicOptionValue/fullscreen; setBasicOptionValue/fullscreen/off; setBasicOptionValue/fullscreen/on` |
| `item_icon_chk` | rads | 進行状態アイコン | `-` | `-` |
| `item_qmlk_chk` | rads | 画面下部ＵＩ | `-` | `-` |
| `item_toch_chk` | rads | タッチＵＩ | `-` | `-` |
| `item_vprg_chk` | rads | 進行メーター | `-` | `-` |
| `noeffect_off` | rad | ＯＮ | `noeffect` | `selectBasicOptionValue/noeffect; setBasicOptionValue/noeffect/off; setBasicOptionValue/noeffect/on` |
| `noeffect_on` | rad | ＯＦＦ | `noeffect` | `selectBasicOptionValue/noeffect; setBasicOptionValue/noeffect/off; setBasicOptionValue/noeffect/on` |
| `panictype_0` | rad | 最小化 | `-` | `selectBasicOptionValue/panictype; setBasicOptionValue/panictype/0; setBasicOptionValue/panictype/1` |
| `panictype_1` | rad | 画像１ | `-` | `selectBasicOptionValue/panictype; setBasicOptionValue/panictype/0; setBasicOptionValue/panictype/1` |
| `panictype_2` | rad | 画像２ | `-` | `selectBasicOptionValue/panictype; setBasicOptionValue/panictype/0; setBasicOptionValue/panictype/1` |
| `panictype_3` | rad | ユーザー指定 | `-` | `selectBasicOptionValue/panictype; setBasicOptionValue/panictype/0; setBasicOptionValue/panictype/1` |
| `qcpopover_off` | rad | 右クリック | `-` | `selectBasicOptionValue/qcpopover; setBasicOptionValue/qcpopover/off; setBasicOptionValue/qcpopover/on` |
| `qcpopover_on` | rad | マウスオーバー | `-` | `selectBasicOptionValue/qcpopover; setBasicOptionValue/qcpopover/off; setBasicOptionValue/qcpopover/on` |
| `scanim_off` | rad | ＯＦＦ | `scanim` | `changeSysArg/false/scanim; changeSysArg/toggle/scanim; changeSysArg/true/scanim` |
| `scanim_on` | rad | ＯＮ | `scanim` | `changeSysArg/false/scanim; changeSysArg/toggle/scanim; changeSysArg/true/scanim` |
| `sqscr` | bool | 画面切り替え | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `sqscr_off` | rad | １６：９ | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `sqscr_on` | rad | ４：３ | `sqscr` | `changeSysArg/false/sqscr; changeSysArg/toggle/sqscr; changeSysArg/true/sqscr` |
| `stayontop_off` | rad | ＯＦＦ | `stayontop` | `changeSysArg/false/stayontop; changeSysArg/toggle/stayontop; changeSysArg/true/stayontop` |
| `stayontop_on` | rad | ＯＮ | `stayontop` | `changeSysArg/false/stayontop; changeSysArg/toggle/stayontop; changeSysArg/true/stayontop` |

## Tab 2：ゲーム進行１

- PBD：`option_03_jp.pbd`
- help：`ゲーム進行`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | 既読自動スキップ／ジャンプ | `-` | `-` |
| `label_b` | label | 既読自動スキップ／ジャンプ 機能選択 | `-` | `-` |
| `label_c` | label | マウスカーソル自動移動 | `-` | `-` |
| `label_d` | label | マウスカーソル自動移動場所 | `-` | `-` |
| `label_e` | label | マウスカーソル自動消去 | `-` | `-` |
| `label_f` | label | セーブ・ロードの実行操作 | `-` | `-` |
| `label_g` | label | Ｈシーン選択肢固定 | `-` | `-` |
| `label_h` | label | フローチャート未到達箇所の表示 | `-` | `-` |
| `label_i` | label | 非アクティブ時動作 | `-` | `-` |
| `label_j` | label | プレビュー表示機能 | `-` | `-` |
| `label_k` | label | サスペンド機能 | `-` | `-` |
| `curhidestep_0` | rad | しない | `-` | `-` |
| `curhidestep_10` | rad | １０秒 | `-` | `-` |
| `curhidestep_20` | rad | ２０秒 | `-` | `-` |
| `curhidestep_5` | rad | ５秒 | `-` | `-` |
| `curmove_off` | rad | ＯＦＦ | `curmove` | `changeSysArg/false/curmove; changeSysArg/toggle/curmove; changeSysArg/true/curmove` |
| `curmove_on` | rad | ＯＮ | `curmove` | `changeSysArg/false/curmove; changeSysArg/toggle/curmove; changeSysArg/true/curmove` |
| `curmoveyes_off` | rad | いいえ | `curmove` | `selectBasicOptionValue/curmoveyes; setBasicOptionValue/curmoveyes/off; setBasicOptionValue/curmoveyes/on` |
| `curmoveyes_on` | rad | はい | `curmove` | `selectBasicOptionValue/curmoveyes; setBasicOptionValue/curmoveyes/off; setBasicOptionValue/curmoveyes/on` |
| `filedclk_off` | rad | シングルクリック | `saveLoadDblClick` | `selectBasicOptionValue/filedclk; setBasicOptionValue/filedclk/off; setBasicOptionValue/filedclk/on` |
| `filedclk_on` | rad | ダブルクリック | `saveLoadDblClick` | `selectBasicOptionValue/filedclk; setBasicOptionValue/filedclk/off; setBasicOptionValue/filedclk/on` |
| `flowshow_off` | rad | ＯＦＦ | `flowchartForceItemOpen` | `selectBasicOptionValue/flowshow; setBasicOptionValue/flowshow/off; setBasicOptionValue/flowshow/on` |
| `flowshow_on` | rad | ＯＮ | `flowchartForceItemOpen` | `selectBasicOptionValue/flowshow; setBasicOptionValue/flowshow/off; setBasicOptionValue/flowshow/on` |
| `hmou_off` | rad | 顔面射精 | `-` | `selectBasicOptionValue/hmou; setBasicOptionValue/hmou/off; setBasicOptionValue/hmou/on` |
| `hmou_on` | rad | 口内射精 | `-` | `selectBasicOptionValue/hmou; setBasicOptionValue/hmou/off; setBasicOptionValue/hmou/on` |
| `hout_off` | rad | 中出し | `-` | `selectBasicOptionValue/hout; setBasicOptionValue/hout/off; setBasicOptionValue/hout/on` |
| `hout_on` | rad | 外出し | `-` | `selectBasicOptionValue/hout; setBasicOptionValue/hout/off; setBasicOptionValue/hout/on` |
| `hsel_off` | rad | ＯＦＦ | `-` | `selectBasicOptionValue/hsel; setBasicOptionValue/hsel/off; setBasicOptionValue/hsel/on` |
| `hsel_on` | rad | ＯＮ | `-` | `selectBasicOptionValue/hsel; setBasicOptionValue/hsel/off; setBasicOptionValue/hsel/on` |
| `icpreview_off` | rad | ＯＮ | `appIconicPreview` | `selectBasicOptionValue/icpreview; setBasicOptionValue/icpreview/off; setBasicOptionValue/icpreview/on` |
| `icpreview_on` | rad | ＯＦＦ | `appIconicPreview` | `selectBasicOptionValue/icpreview; setBasicOptionValue/icpreview/off; setBasicOptionValue/icpreview/on` |
| `readjump_off` | rad | スキップ | `-` | `selectBasicOptionValue/readjump; setBasicOptionValue/readjump/off; setBasicOptionValue/readjump/on` |
| `readjump_on` | rad | ジャンプ | `-` | `selectBasicOptionValue/readjump; setBasicOptionValue/readjump/off; setBasicOptionValue/readjump/on` |
| `readskip_off` | rad | ＯＦＦ | `afterskip` | `selectBasicOptionValue/readskip; setBasicOptionValue/readskip/off; setBasicOptionValue/readskip/on` |
| `readskip_on` | rad | ＯＮ | `afterskip` | `selectBasicOptionValue/readskip; setBasicOptionValue/readskip/off; setBasicOptionValue/readskip/on` |
| `stopdeactive_off` | rad | 継続 | `stopdeactive` | `changeSysArg/false/stopdeactive; changeSysArg/toggle/stopdeactive; changeSysArg/true/stopdeactive` |
| `stopdeactive_on` | rad | 停止 | `stopdeactive` | `changeSysArg/false/stopdeactive; changeSysArg/toggle/stopdeactive; changeSysArg/true/stopdeactive` |
| `suspend_off` | rad | ＯＦＦ | `suspendBootEnabled` | `selectBasicOptionValue/suspend; setBasicOptionValue/suspend/off; setBasicOptionValue/suspend/on` |
| `suspend_on` | rad | ＯＮ | `suspendBootEnabled` | `selectBasicOptionValue/suspend; setBasicOptionValue/suspend/off; setBasicOptionValue/suspend/on` |

## Tab 3：ゲーム進行２

- PBD：`option_04_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | ゲーム再生速度 | `-` | `-` |
| `label_b` | label | 音声再生速度 | `-` | `-` |
| `label_c` | label | スキップ速度調整 | `-` | `-` |
| `label_d` | label | スキップスタイル | `-` | `-` |
| `label_e` | label | 右クリックでのムービースキップ | `-` | `-` |
| `label_f` | label | スキップ時のムービースキップ | `-` | `-` |
| `label_g` | label | テキストウインドウ表示（ドラマチックモード） | `-` | `-` |
| `label_g1` | label | ボイスありのセリフ（主人公以外のセリフ） | `-` | `-` |
| `label_g2` | label | ボイスなしのセリフ（主人公のセリフ） | `-` | `-` |
| `label_g3` | label | その他のテキスト | `-` | `-` |
| `label_h` | label | スクリーンショット保存設定 | `-` | `-` |
| `dramatic_chk` | check | 旧ドラマチックモード設定 | `drama` | `selectBasicOptionValue/dramatic; setBasicOptionValue/dramatic/off; setBasicOptionValue/dramatic/on` |
| `drawspeed` | slider | ゲーム再生速度 | `drawspeed` | `onSpeedSliderChange` |
| `movierclick_off` | rad | ＯＦＦ | `movieRClickSkip` | `selectBasicOptionValue/movierclick; setBasicOptionValue/movierclick/off; setBasicOptionValue/movierclick/on` |
| `movierclick_on` | rad | ＯＮ | `movieRClickSkip` | `selectBasicOptionValue/movierclick; setBasicOptionValue/movierclick/off; setBasicOptionValue/movierclick/on` |
| `movieskip_off` | rad | ＯＦＦ | `movieSkipOnSkip` | `selectBasicOptionValue/movieskip; setBasicOptionValue/movieskip/off; setBasicOptionValue/movieskip/on` |
| `movieskip_on` | rad | ＯＮ | `movieSkipOnSkip` | `selectBasicOptionValue/movieskip; setBasicOptionValue/movieskip/off; setBasicOptionValue/movieskip/on` |
| `skipspeed` | slider | スキップ速度調整 | `skipspeed` | `onSpeedSliderChange` |
| `skipst_0` | rad | ノーマル | `-` | `selectBasicOptionValue/skipst; setBasicOptionValue/skipst/0; setBasicOptionValue/skipst/1` |
| `skipst_1` | rad | ファスト | `-` | `selectBasicOptionValue/skipst; setBasicOptionValue/skipst/0; setBasicOptionValue/skipst/1` |
| `skipst_2` | rad | テキスト | `-` | `selectBasicOptionValue/skipst; setBasicOptionValue/skipst/0; setBasicOptionValue/skipst/1` |
| `snapdetail` | rbt | 詳細設定 | `-` | `-` |
| `snapsilent_off` | rad | 毎回ファイル名を指定 | `-` | `-` |
| `snapsilent_on` | rad | 日付ファイル名で保存 | `-` | `-` |
| `txv_novo_0` | rad | 常に表示 | `-` | `-` |
| `txv_novo_1` | rad | オート時のみ非表示 | `-` | `-` |
| `txv_novo_2` | rad | 常に非表示 | `-` | `-` |
| `txv_other_0` | rad | 常に表示 | `-` | `-` |
| `txv_other_1` | rad | オート時のみ非表示 | `-` | `-` |
| `txv_other_2` | rad | 常に非表示 | `-` | `-` |
| `txv_voice_0` | rad | 常に表示 | `-` | `-` |
| `txv_voice_1` | rad | オート時のみ非表示 | `-` | `-` |
| `txv_voice_2` | rad | 常に非表示 | `-` | `-` |
| `use_speech` | check | 外部音声ツールを連動 | `-` | `-` |
| `vspeedsync_chk` | check | ゲーム再生速度と連動 | `voicespeed` | `selectBasicOptionValue/vspeedsync; setBasicOptionValue/vspeedsync/off; setBasicOptionValue/vspeedsync/on` |

## Tab 4：テキスト

- PBD：`option_05_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | テキスト速度 | `-` | `-` |
| `label_a1` | label | １文字あたりの待ち時間 | `-` | `-` |
| `label_a2` | label | 基本待ち時間 | `-` | `-` |
| `label_b` | label | オート速度 | `-` | `-` |
| `label_c` | label | オートモードパターン | `-` | `-` |
| `label_d1` | label | 未読スキップ | `-` | `-` |
| `label_d2` | label | 選択肢後スキップ | `-` | `-` |
| `label_e1` | label | Ｃｔｒｌスキップ | `-` | `-` |
| `label_e2` | label | 選択肢後オート | `-` | `-` |
| `label_f1` | label | ウインドウ・文字設定 | `-` | `-` |
| `label_f2` | label | カラー設定 | `-` | `-` |
| `label_g` | label | ウインドウ透明度 | `-` | `-` |
| `afterauto_off` | rad | 解除 | `-` | `selectBasicOptionValue/afterauto; setBasicOptionValue/afterauto/off; setBasicOptionValue/afterauto/on` |
| `afterauto_on` | rad | 継続 | `-` | `selectBasicOptionValue/afterauto; setBasicOptionValue/afterauto/off; setBasicOptionValue/afterauto/on` |
| `afterskip_off` | rad | 解除 | `-` | `selectBasicOptionValue/afterskip; setBasicOptionValue/afterskip/off; setBasicOptionValue/afterskip/on` |
| `afterskip_on` | rad | 継続 | `-` | `selectBasicOptionValue/afterskip; setBasicOptionValue/afterskip/off; setBasicOptionValue/afterskip/on` |
| `autospeed` | slider | オート速度 | `autoModeChWait` | `onSpeedSliderChange` |
| `autovwait_0` | rad | ノーマルモード | `-` | `selectBasicOptionValue/autovwait; setBasicOptionValue/autovwait/0; setBasicOptionValue/autovwait/1` |
| `autovwait_1` | rad | ボイスモード | `-` | `selectBasicOptionValue/autovwait; setBasicOptionValue/autovwait/0; setBasicOptionValue/autovwait/1` |
| `autovwait_2` | rad | スピードモード | `-` | `selectBasicOptionValue/autovwait; setBasicOptionValue/autovwait/0; setBasicOptionValue/autovwait/1` |
| `color_hwin` | rad | Ｈシーン時ウインドウ | `-` | `-` |
| `color_owin` | rad | 視点変更時ウインドウ | `-` | `-` |
| `color_read` | rad | 既読文字 | `-` | `-` |
| `color_text` | rad | 未読文字 | `-` | `-` |
| `color_win` | rad | 通常時ウインドウ | `-` | `-` |
| `ctrlskip_off` | rad | 既読のみ | `-` | `selectBasicOptionValue/ctrlskip; setBasicOptionValue/ctrlskip/off; setBasicOptionValue/ctrlskip/on` |
| `ctrlskip_on` | rad | すべて | `-` | `selectBasicOptionValue/ctrlskip; setBasicOptionValue/ctrlskip/off; setBasicOptionValue/ctrlskip/on` |
| `fontselect` | rbt | フォント選択 | `-` | `-` |
| `hsv_reset` | rbt | リセット | `-` | `-` |
| `nohwindow_chk` | check | Ｈシーン時ウインドウの無効化 | `-` | `selectBasicOptionValue/nohwindow; setBasicOptionValue/nohwindow/off; setBasicOptionValue/nohwindow/on` |
| `skipall` | bool | 未読スキップ | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `skipall_off` | rad | 既読のみ | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `skipall_on` | rad | すべて | `allskip` | `selectBasicOptionValue/skipall; setBasicOptionValue/skipall/off; setBasicOptionValue/skipall/on` |
| `textspeed` | slider | テキスト速度 | `userChSpeed` | `onSpeedSliderChange` |

## Tab 5：サウンド

- PBD：`option_06_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | システムボイス個別設定 | `-` | `-` |
| `label_b` | label | キャラクター選択 | `-` | `-` |
| `label_b1` | label | ＢＧＭ | `-` | `-` |
| `label_b2` | label | ＢＧＭ（ボイス再生時） | `-` | `-` |
| `label_c1` | label | ムービー | `-` | `-` |
| `label_c2` | label | 演奏 | `-` | `-` |
| `label_d1` | label | ＢＧＶ（通常シーン） | `-` | `-` |
| `label_d2` | label | ＢＧＶ（Ｈシーン） | `-` | `-` |
| `label_e1` | label | ボイスカット | `-` | `-` |
| `label_e2` | label | ボイスエフェクト | `-` | `-` |
| `label_f1` | label | ボイス（ゲーム中） | `-` | `-` |
| `label_f2` | label | ＳＥ（ゲーム効果音） | `-` | `-` |
| `label_g` | label | 音声の個別設定 | `-` | `-` |
| `label_h` | label | システム音選択 | `-` | `-` |
| `label_i1` | label | ＳＥ（システム効果音） | `-` | `-` |
| `label_i2` | label | システムボイス | `-` | `-` |
| `bgm` | slider | ＢＧＭ | `bgm.volume` | `onAudioVolumeChange; setAudioOnOff/bgm/0; setAudioOnOff/bgm/1` |
| `chv` | - | - | `-` | `-` |
| `chv0` | check | 陽見 恵凪 | `-` | `-` |
| `chv1` | check | 隠 杏珠 | `-` | `-` |
| `chv10` | check | その他(男性) | `-` | `-` |
| `chv11` | check | その他(女性) | `-` | `-` |
| `chv2` | check | 嶌越 月望 | `-` | `-` |
| `chv3` | check | 二見原 莉々子 | `-` | `-` |
| `chv4` | check | 礫川 美玖 | `-` | `-` |
| `chv5` | check | 茶園 那優花 | `-` | `-` |
| `chv6` | check | 不二 衛哉 | `-` | `-` |
| `chv7` | check | 礫川 傑 | `-` | `-` |
| `chv8` | check | 礫川 雄真 | `-` | `-` |
| `chv9` | check | 仲原 大夢 | `-` | `-` |
| `chv_off` | rad | ＯＦＦ | `-` | `-` |
| `chv_on` | rad | ＯＮ | `-` | `-` |
| `down` | slider | - | `bgmdownlevel` | `onAudioVolumeChange; setAudioOnOff/down/0; setAudioOnOff/down/1` |
| `down_mute` | check | 無効にする" # "ＢＧＭダウンを無効にする | `bgmdownlevel` | `onAudioVolumeChange; setAudioOnOff/down/0; setAudioOnOff/down/1` |
| `lowprisysvo_chk` | check | 本編ボイス再生中はシステムボイスを再生しない | `-` | `selectBasicOptionValue/lowprisysvo; setBasicOptionValue/lowprisysvo/off; setBasicOptionValue/lowprisysvo/on` |
| `lvaudiosample_chk` | check | 音量サンプル再生 | `-` | `selectBasicOptionValue/lvaudiosample; setBasicOptionValue/lvaudiosample/off; setBasicOptionValue/lvaudiosample/on` |
| `movie` | slider | ムービー | `movie.volume` | `onAudioVolumeChange; setAudioOnOff/movie/0; setAudioOnOff/movie/1` |
| `mvaudiosample_chk` | check | 音量サンプル再生 | `movieAudioSample` | `selectBasicOptionValue/mvaudiosample; setBasicOptionValue/mvaudiosample/off; setBasicOptionValue/mvaudiosample/on` |
| `sysse` | slider | - | `sysse.volume` | `onAudioVolumeChange; setAudioOnOff/sysse/0; setAudioOnOff/sysse/1` |
| `sysse_play` | rad | 効果音 | `sysse.volume` | `onAudioVolumeChange; setAudioOnOff/sysse/0; setAudioOnOff/sysse/1` |
| `sysvo` | slider | - | `sysvo.volume` | `onAudioVolumeChange; setAudioOnOff/sysvo/0; setAudioOnOff/sysvo/1` |
| `sysvo0_chk` | svnm | 恵凪 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo1_chk` | svnm | 杏珠 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo2_chk` | svnm | 月望 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo3_chk` | svnm | 莉々子 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo4_chk` | svnm | 美玖 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo5_chk` | svnm | 那優花 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo6_chk` | svnm | 衛哉 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo7_chk` | svnm | 傑 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo8_chk` | svnm | 雄真 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo9_chk` | svnm | 大夢 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvo_ok` | rbt | 戻る | `sysvo.volume` | `onAudioVolumeChange; setAudioOnOff/sysvo/0; setAudioOnOff/sysvo/1` |
| `sysvo_play` | rad | キャラボイス | `sysvo.volume` | `onAudioVolumeChange; setAudioOnOff/sysvo/0; setAudioOnOff/sysvo/1` |
| `sysvoall_off` | rad | すべてＯＦＦ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoall_on` | rad | すべてＯＮ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvodetail` | rbt | 詳細設定 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay0_chk` | check | ATTENTION読み上げ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay10_chk` | check | システム設定 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay11_chk` | check | システム設定個別ページ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay12_chk` | check | エクストラモード | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay13_chk` | check | アフターストーリー | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay14_chk` | check | 確認ダイアログ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay15_chk` | check | ゲーム終了時 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay1_chk` | check | ブランドロゴ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay2_chk` | check | タイトル画面 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay3_chk` | check | ボタンカスタマイズ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay4_chk` | check | セーブ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay5_chk` | check | ロード | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay6_chk` | check | お気に入りボイス | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay7_chk` | check | ボイス登録 | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay8_chk` | check | バックログ | `sysvo.volume` | `onAudioVolumeChange` |
| `sysvoplay9_chk` | check | フローチャート | `sysvo.volume` | `onAudioVolumeChange` |
| `voicecut_off` | rad | ＯＦＦ | `voice.volume` | `selectBasicOptionValue/voicecut; setBasicOptionValue/voicecut/off; setBasicOptionValue/voicecut/on` |
| `voicecut_on` | rad | ＯＮ | `voice.volume` | `selectBasicOptionValue/voicecut; setBasicOptionValue/voicecut/off; setBasicOptionValue/voicecut/on` |
| `voiceeff_off` | rad | ＯＦＦ | `voice.volume` | `selectBasicOptionValue/voiceeff; setBasicOptionValue/voiceeff/off; setBasicOptionValue/voiceeff/on` |
| `voiceeff_on` | rad | ＯＮ | `voice.volume` | `selectBasicOptionValue/voiceeff; setBasicOptionValue/voiceeff/off; setBasicOptionValue/voiceeff/on` |

## Tab 6：ダイアログ

- PBD：`option_07_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_l1a` | label | セーブ実行確認 | `-` | `-` |
| `label_l1b` | label | セーブの上書き確認 | `-` | `-` |
| `label_l1c` | label | ダイレクトセーブ実行確認 | `-` | `-` |
| `label_l1d` | label | ロード実行確認 | `-` | `-` |
| `label_l1e` | label | クイックセーブ実行確認 | `-` | `-` |
| `label_l1f` | label | クイックロード実行確認 | `-` | `-` |
| `label_l1g` | label | タイトルに戻る・回想中断実行確認 | `-` | `-` |
| `label_l2a` | label | バックログジャンプ・ボイス回想実行確認 | `-` | `-` |
| `label_l2b` | label | フローチャートジャンプ実行確認 | `-` | `-` |
| `label_l2c` | label | 次の選択肢に進む実行確認 | `-` | `-` |
| `label_l2d` | label | 前の選択肢に戻る実行確認 | `-` | `-` |
| `label_l2e` | label | 次のシーンに進む実行確認 | `-` | `-` |
| `label_l2f` | label | 前のシーンに戻る実行確認 | `-` | `-` |
| `label_l2g` | label | お気に入りボイス登録実行確認 | `-` | `-` |
| `label_l3a` | label | システム初期化実行確認 | `-` | `-` |
| `label_l3b` | label | 立ち絵鑑賞初期化実行確認 | `-` | `-` |
| `label_l3c` | label | セーブデータ削除実行確認 | `-` | `-` |
| `label_l3d` | label | セーブデータ入れ替え実行確認 | `-` | `-` |
| `label_l3e` | label | セーブデータコピー実行確認 | `-` | `-` |
| `label_l3f` | label | ゲーム終了実行確認 | `-` | `-` |
| `label_l3g` | label | サスペンド機能実行確認 | `-` | `-` |
| `cf_backto_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_backto_on` | rad | ＯＮ | `-` | `-` |
| `cf_copy_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_copy_on` | rad | ＯＮ | `-` | `-` |
| `cf_delete_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_delete_on` | rad | ＯＮ | `-` | `-` |
| `cf_dsave_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_dsave_on` | rad | ＯＮ | `-` | `-` |
| `cf_exit_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_exit_on` | rad | ＯＮ | `-` | `-` |
| `cf_flow_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_flow_on` | rad | ＯＮ | `-` | `-` |
| `cf_init_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_init_on` | rad | ＯＮ | `-` | `-` |
| `cf_initstand_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_initstand_on` | rad | ＯＮ | `-` | `-` |
| `cf_jump_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_jump_on` | rad | ＯＮ | `-` | `-` |
| `cf_load_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_load_on` | rad | ＯＮ | `-` | `-` |
| `cf_next_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_next_on` | rad | ＯＮ | `-` | `-` |
| `cf_nextscn_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_nextscn_on` | rad | ＯＮ | `-` | `-` |
| `cf_overwrite_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_overwrite_on` | rad | ＯＮ | `-` | `-` |
| `cf_prevscn_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_prevscn_on` | rad | ＯＮ | `-` | `-` |
| `cf_qload_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_qload_on` | rad | ＯＮ | `-` | `-` |
| `cf_qsave_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_qsave_on` | rad | ＯＮ | `-` | `-` |
| `cf_resume_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_resume_on` | rad | ＯＮ | `-` | `-` |
| `cf_save_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_save_on` | rad | ＯＮ | `-` | `-` |
| `cf_swap_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_swap_on` | rad | ＯＮ | `-` | `-` |
| `cf_title_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_title_on` | rad | ＯＮ | `-` | `-` |
| `cf_vsave_off` | rad | ＯＦＦ | `-` | `-` |
| `cf_vsave_on` | rad | ＯＮ | `-` | `-` |
| `cfall_off` | rad | すべてＯＦＦ | `-` | `-` |
| `cfall_on` | rad | すべてＯＮ | `-` | `-` |

## Tab 7：マウス

- PBD：`option_08_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | マウスジェスチャー | `-` | `-` |
| `label_b` | label | コマンドパレット | `-` | `-` |
| `gsenable_rev` | check | ジェスチャー機能の無効化 | `-` | `selectBasicOptionValue/gsenable; setBasicOptionValue/gsenable/off; setBasicOptionValue/gsenable/on` |

## Tab 8：キーボード

- PBD：`option_09_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_l1a` | label | セーブ画面へ | `-` | `-` |
| `label_l1b` | label | ロード画面へ | `-` | `-` |
| `label_l1c` | label | ダイレクトセーブ | `-` | `-` |
| `label_l1d` | label | クイックセーブ | `-` | `-` |
| `label_l1e` | label | クイックロード | `-` | `-` |
| `label_l1f` | label | システム設定画面へ | `-` | `-` |
| `label_l1g` | label | 画面サイズ切り替え | `-` | `-` |
| `label_l1h` | label | メッセージ送り・決定 | `-` | `-` |
| `label_l1i` | label | オートモード | `-` | `-` |
| `label_l1j` | label | スキップモード | `-` | `-` |
| `label_l1k` | label | Ｃｔｒｌスキップ | `-` | `-` |
| `label_l2a` | label | 次のシーンに進む | `-` | `-` |
| `label_l2b` | label | 次の選択肢に進む | `-` | `-` |
| `label_l2c` | label | バックログ画面へ | `-` | `-` |
| `label_l2d` | label | バックログ時１画面分上移動 | `-` | `-` |
| `label_l2e` | label | バックログ時１画面分下移動 | `-` | `-` |
| `label_l2f` | label | １つ前のテキストに戻る | `-` | `-` |
| `label_l2g` | label | バックスキップ | `-` | `-` |
| `label_l2h` | label | 前のシーンに戻る | `-` | `-` |
| `label_l2i` | label | 前の選択肢に戻る | `-` | `-` |
| `label_l2j` | label | フローチャート画面へ | `-` | `-` |
| `label_l2k` | label | タイトル画面へ | `-` | `-` |
| `label_l3a` | label | ボリューム調整 | `-` | `-` |
| `label_l3b` | label | ウインドウ非表示 | `-` | `-` |
| `label_l3c` | label | 音声リピート再生 | `-` | `-` |
| `label_l3d` | label | お気に入りボイスの登録 | `-` | `-` |
| `label_l3e` | label | お気に入りボイス画面へ | `-` | `-` |
| `label_l3f` | label | スクリーンショット | `-` | `-` |
| `label_l3g` | label | スクランブル | `-` | `-` |
| `label_l3h` | label | 割り当て可能キー一覧および解除 | `-` | `-` |

## Tab 9：ゲームパッド

- PBD：`option_10_jp.pbd`
- help：`-`

| 控件 ID | 类型 | 日文标签 | 变量 | API/绑定 |
|---------|------|----------|------|----------|
| `label_a` | label | ゲームパッド | `-` | `-` |
| `label_b` | label | コマンドパレット | `-` | `-` |
| `engamepad_rev` | check | ゲームパッド操作を無効化 | `-` | `selectBasicOptionValue/engamepad; setBasicOptionValue/engamepad/off; setBasicOptionValue/engamepad/on` |
| `gamepad_assign` | rbt | ボタンを再配置 | `-` | `-` |

## 解码说明

- `uitexts.toml` / `help_opt.txt` 在 krkrz_dump 中仍为 yuzuex 头，需 `simple_crypt.decode()` 后再按 UTF-16-LE 读取。
- 静态 `utf-16-le skip` 解码会得到乱码；不要与 simple_crypt 结果混用。
- 部分标签仍烤在 `option_xx_jp__pack.tlg` 图里；本表以 `uitexts.toml` 动态文本为准。
