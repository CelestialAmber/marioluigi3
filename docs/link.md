# Link
This file documents technical information about Link.
- [States](#states)
- [State hierarchy](#state-hierarchy)

## State handlers
State handlers contain data and functions to process Link's state. Only one state handler is active at a time, but data can be
shared outside of the active state handler.

 Index | Name                | Description
-------|---------------------|-------------
0      | `LinkStateMove`     | Handles Link's movement.
1      | `LinkStateItem`     | Handles item usage, including sword and shield.
2      | `LinkStateInteract` | Handles talking to NPCs and grabbing/pushing/pulling objects.
3      | `LinkStateFollow`   | Handles moving toward objects.
4      | `LinkStateRoll`     | Handles rolling and dizziness.
5      | `LinkStateDamage`   | Handles receiving damage and knockback.
6      | `LinkStateCutscene` | Handles being in a cutscene, transitions into new scenes and getting items.

## State hierarchy
Link's states are organized in a hierarchical structure. Similar to actor IDs, states are labelled by 4-character IDs. In
addition, the states have names in Japanese.

> [!NOTE]
> The hierarchy and Japanese names were likely used for debugging and may have no meaning in the actual game engine.

- `PLYR`: Player
    - `PLNK`: Link motion (リンクモーション)
        - `LGNR`: General (全般)
        - `LWIT`: Wait (ウェイト)
        - `LMOV`: Move (移動)
        - `LROL`: Roll (前転)
        - `LAJP`: Auto-jump (オートジャンプ)
        - `LATK`: Attack (剣振り)
            - `LVAT`: Vertical attack (縦切り)
            - `LLAT`: Horizontal attack (横切り)
            - `LSAT`: Stab attack (突き)
            - `LTAT`: Spin attack (回転切り)
            - `LARB`: Recoil (反動)
        - `LJAT`: Jump attack (ジャンプ切り)
        - `LDFC`: Defence (防御)
        - `LDMG`: Damage (ダメージ)
        - `LGRB`: Grab (持ち上げ)
        - `LPSH`: Push/pull (押し引き)
        - `LIGT`: Item get (アイテムゲット)
        - `LNAV`: Navi (精霊)
        - `LBOW`: Bow (弓矢)
        - `LBMR`: Boomerang (ブーメラン)
        - `LHMR`: Hammer (ハンマー)
        - `LROP`: Rope (ロープ)
        - `LSCP`: Scoop (スコップ)
        - `LOIT`: Other item (他のアイテム)
        - `LABN`: Abnormal state (状態異常)
        - `LLOT`: Other (その他)
    - `PTMP`: Temporary (一時調整)
    - `PEFT`: Effect (エフェクト)

The states can also be found in `Player/motion.bhio` in the assets. The file appears to contain configurable properties for
some of the states. The properties are labelled with up to 12 bytes (6 characters) of Japanese text, causing some labels to be cut off.

State  | Property                 | Type    | Value | Japanese
-------|--------------------------|---------|-------|----------
`LGNR` | Shadow darkness          | `int`   | 26    | 影の濃さ
`LGNR` | Model type               | `int`   | 2     | モデルタイプ
`LGNR` | Semi-transparent model   | `int`   | 11    | 半透明モデル
`LGNR` | Semi-transparent R       | `int`   | 31    | 半透明Ｒ
`LGNR` | Semi-transparent G       | `int`   | 31    | 半透明Ｇ
`LGNR` | Semi-transparent B       | `int`   | 31    | 半透明Ｂ
`LGNR` | Area change              | `int`   | 15    | エリア替えフ
`LGNR` | Stairway fade            | `int`   | 10    | 階段フェード
`LGNR` | Other ho...              | `int`   | 13    | その他フェー
`LGNR` | Area movement offset     | `20.12` | 1.9   | エリア移動オ
`LDMG` | Damage tie...            | `int`   | 0     | ダメージタイ
`LDMG` | Small damage speed       | `20.12` | 2.0   | 小ダメ再生速
`LDMG` | Small damage start frame | `20.12` | 0.0   | 小ダメ開始フ
`LDMG` | Small damage end frame   | `20.12` | 10.0  | 小ダメ終了フ
`LDMG` | ???                      | `int`   | 6     | ビリビリ回数
`LDMG` | ???                      | `20.12` | 1.0   | ビリビリ再生
`LDMG` | ???                      | `20.12` | 1.23  | 吹き上げ高さ
`LDMG` | ???                      | `20.12` | 0.2   | 吹き上げふっ
`LDMG` | ???                      | `20.12` | 0.2   | フリック跳び
`LDMG` | Ice damage?              | `int`   | 60    | 凍りダメージ
`LGRB` | Grab speed               | `20.12` | 1.6   | 持ち上げ再生
`LGRB` | Grab start               | `20.12` | 2.0   | 持ち上げ開始
`LGRB` | Grab end                 | `20.12` | 10.0  | 持ち上げ終了
`LGRB` | Throw speed              | `20.12` | 1.0   | 投げ再生速度
`LGRB` | Throw start frame        | `20.12` | 0.0   | 投げ開始フレ
`LGRB` | Throw end frame          | `20.12` | 15.0  | 投げ終了フレ
`LGRB` | Throw frame              | `20.12` | 2.0   | 投げ離れフレ
`LPSH` | Stop time                | `int`   | 3     | 停止時間
`LPSH` | Direct push              | `20.12` | 0.5   | ダイレクトプ
`LIGT` | X-offset                 | `20.12` | 0.368 | オフセットＸ
`LIGT` | Y-offset                 | `20.12` | 1.323 | オフセットＹ
`LIGT` | Z-offset                 | `20.12` | 0.05  | オフセットＺ
`LIGT` | Rotation speed           | `20.12` | 0.066 | 回転速度
`LROP` | Rope width               | `20.12` | 0.12  | ロープ幅
`LROP` | Texture...               | `20.12` | 30.0  | テクスチャリ
`LROP` | High jump                | `20.12` | 0.54  | ハイジャンプ
`LROP` | Lean depth?              | `20.12` | 0.6   | 寄りかかり深
`LLOT` | Breath start frame       | `20.12` | 0.0   | 息吹き開始フ
`LLOT` | Breath end frame         | `20.12` | 10.0  | 息吹き終了フ
`LLOT` | Walk offset              | `20.12` | 1.1   | 歩きオフセッ
`LLOT` | Run offset               | `20.12` | 1.7   | 走りオフセッ
`LLOT` | Stairway offset          | `20.12` | 1.0   | 階段オフセッ
`LLOT` | Player ...               | `20.12` | 0.01  | プレイヤー消
`LLOT` | Warp ho...               | `int`   | 55    | ワープフェー
`LLOT` | Player ...               | `int`   | 10    | プレイヤー半
`LLOT` | Warp rise                | `20.12` | 0.03  | ワープ浮き上
