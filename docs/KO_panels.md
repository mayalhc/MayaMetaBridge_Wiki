# 패널 레퍼런스

[English](panels.md)

플러그인의 모든 패널을 한 장씩. 무엇을 위한 것인지, 어떻게 생겼는지, 어떤 컨트롤을 그리는지.

이 문서는 `tools/guide_panels.py`가 플러그인 자체의 레지스트리에서 생성합니다. 레지스트리가 바뀌면 다시 생성하세요.

---

## 1. MetaBridge DNA

패널 키: `main`

MetaHuman 어셈블러. 폴더를 가리키고 그 안의 캐릭터를 목록으로 받아 하나를 씬에 만듭니다. 얼굴 리그와 mGear 리그의 프레임도 여기 있습니다.

![MetaBridge DNA](assets/panel_main.png)

### MetaHuman Assembler

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Refresh Character List | `mmb_mh_scan_dir` |
| Re-Assemble | `mmb_mh_assemble` |
| Assemble | `mmb_mh_assemble` |
| New | `mmb_mh_new` |
| Load Head DNA... | `mmb_load_head_dna` |
| Load Body DNA... | `mmb_load_body_dna` |
| Activate Slot | `mmb_mh_activate_slot` |
| Toggle Face Rig | `mmb_toggle_face_rig_slot` |
| Delete Slot | `mmb_mh_delete_slot` |
| Relink DNA | `mmb_relink_dna` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| MetaHumans Directory | 텍스트 | — | — | `ml_mh_dir` |
| Head | 체크박스 | on | — | `ml_mh_load_head` |
| Body | 체크박스 | on | — | `ml_mh_load_body` |
| Textures | 체크박스 | on | — | `ml_mh_load_textures` |
| LOD | 숫자 | `0` | 0 – 7 | `ml_lod_level` |

**패널이 그리는 안내 문구**

* MetaHumans Directory:
* Set directory above and click
* to scan for MetaHuman folders
* Assembled Characters:

### Face Rig

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Append GUIArmature | `mmb_append_gui_armature` |
| Toggle Face Rig | `mmb_toggle_face_rig_slot` |

### Rigify Body Control Rig

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| 1. Build Meta-Rig | `mmb_build_metarig_only` |
| 2. Generate Control Rig | `mmb_generate_rig_only` |
| Remove Retarget | `mmb_remove_retarget` |
| 3. Apply Retarget | `mmb_apply_retarget` |
| Unlink Head Rig | `mmb_unlink_head_rig` |
| Link Head Rig | `mmb_link_head_rig` |
| Toggle RBF Correctives (Body) | `mmb_toggle_body_correctives_rbf` |
| Body Correctives: none in this DNA | `mmb_toggle_body_correctives_rbf` |
| Show RBF Controls | `mmb_show_rbf_controllers` |
| Hide | `mmb_hide_rbf_controllers` |
| Import FBX Animation... | `mmb_import_fbx_animation` |
| Remove Control Rig | `mmb_remove_cloud_rig` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Driver Bone | 메뉴 | — | 실행 시 생성 | `ml_rbf_driver` |
| ["rbf_influence"] | 목록 | — | — | `["rbf_influence"]` |

**패널이 그리는 안내 문구**

* Rigify: enabled
* Rigify: NOT enabled
* Pick a driver bone above, or select a control and leave it on Auto
* Active RBF Controllers:

### Additional Options

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Toggle IK Stretch | `mmb_toggle_limb_ik_stretch` |
| Toggle Heel Pivot | `mmb_toggle_foot_spin_pivot` |
| Toggle Finger IK | `mmb_toggle_finger_ik` |
| IK to FK | `mmb_finger_ik_fk` |
| FK to IK | `mmb_finger_ik_fk` |
| Snap Fingertip Targets to Pose | `mmb_snap_finger_ik` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| '["%s"]' % _crb._FINGER_IK_PROP | 목록 | — | — | `'["%s"]' % _crb._FINGER_IK_PROP` |

**패널이 그리는 안내 문구**

* Per-finger  (0 = joints, 1 = fingertip)
* Assemble body first
* Enable Rigify: Edit > Preferences > Add-ons
* Search 'Rigify'  →  Rigging: Rigify  →  Enable

### RNA

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Re-Auto Link | `mmb_re_auto_link` |
| Clear All | `mmb_clear_manual` |
| Print Full Map (console) | `mmb_print_gui_map` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| View | 메뉴 | `DNA` | DNA = DNA RC View, BONE = Bone View | `ml_inspector_mode` |
| Filter | 텍스트 | — | — | `ml_rc_filter2` |
| Show | 메뉴 | `ALL` | ALL = All, MAPPED = Mapped, UNMAPPED = Unmapped | `ml_rc_show` |
| Show Parent | 체크박스 | off | — | `ml_show_parent` |
| Per Page | 숫자 | `25` | 10 – 60 | `ml_rc_page_size` |

**패널이 그리는 안내 문구**

* Per page:

### mGear Rig (Maya-only)

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| One-Click mGear Rig | `mmb_mgear_rig` - mGear's MetaHuman guide, snapped to the active character, and mGear's Shifter rig built over it |
| Snap mGear Guide | `mmb_mgear_snap` - put the guide's locators back on the character's joints, for a guide that was placed or edited by hand |
| Bind Head to mGear Rig | `mmb_mgear_bind_head` - constrain the character's head part to the body joints mGear drives, so the face and the expression sliders follow the rig (the one-click does this already) |
| Unbind Head from mGear Rig | `mmb_mgear_unbind_head` - take the head constraints out again; the head keeps its own values where it stands |
| Register Anim Picker | `mmb_mgear_anim_picker` - make mGear's Anim Picker for the MetaHuman rig - the node and the body and face pages - and open it |
| Remove mGear Rig | `mmb_mgear_clear` - delete the guide and the rigs mGear built; the character stays as it is |

### Arnold Look-Dev (Maya-only)

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Arnold Look-Dev | `mmb_arnold_lookdev` - Arnold shaders for the character's materials (the hair included), a key/fill/rim light rig aimed at its face, two cameras framed on it, the render settings a beauty still is rendered at, and a measured exposure - a probe render of the face, solved until the skin lands where a reference still's does, on the GPU |
| Open Arnold RenderView | `mmb_arnold_render_view` - MtoA's RenderView on the look-dev camera, with its interactive render running |
| Remove Look-Dev | `mmb_arnold_lookdev_clear` - the character's own shaders back on their sets, the Arnold ones, the rig and both cameras deleted |

---

## 2. Animation Baker

패널 키: `anim_baker`

프레임 범위에 걸쳐 얼굴 보드의 키를 구워, 표정 연기가 베이크된 애니메이션이 되게 합니다.

![Animation Baker](assets/panel_anim_baker.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Bake Face Animation | `mmb_bake_face_animation` |
| Clear Baked Animation | `mmb_clear_baked_animation` |

**패널이 그리는 안내 문구**

* Keyframe GUI board bones first,
* then bake over the frame range

---

## 3. ARKit Live

패널 키: `arkit_live`

아이폰의 Live Link Face가 보내는 52개 ARKit 블렌드셰이프를 받아 표정 슬라이더를 실시간으로 움직입니다.

![ARKit Live](assets/panel_arkit_live.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Connect | `mmb_arkit_connect` |
| Record | `mmb_arkit_toggle_recording` |
| Load Live Link Face CSV... | `mmb_arkit_load_csv` |
| Export Face CSV... | `mmb_export_face_csv` |
| Export ARKit Blend Shapes (FBX)... | `mmb_export_arkit_blendshapes` |
| Rebuild Name Mapping | `mmb_arkit_rebuild_mapping` |
| Calibrate Neutral Face | `mmb_arkit_calibrate_neutral` |
| Clear Neutral Calibration | `mmb_arkit_clear_calibration` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Host | 텍스트 | `0.0.0.0` | — | `ml_arkit_host` |
| Port | 숫자 | `11111` | 1 – 65535 | `ml_arkit_port` |
| Smoothing | 숫자 | `0.5` | 0 – 0.95 | `ml_arkit_smoothing` |
| Deadzone | 숫자 | `0.0` | 0 – 0.9 | `ml_arkit_deadzone` |
| Gain | 숫자 | `1.0` | 0.1 – 4 | `ml_arkit_gain` |
| Track Head Rotation | 체크박스 | off | — | `ml_arkit_head_tracking` |
| Invert Pitch | 체크박스 | off | — | `ml_arkit_head_invert_pitch` |
| Invert Yaw | 체크박스 | off | — | `ml_arkit_head_invert_yaw` |
| Invert Roll | 체크박스 | off | — | `ml_arkit_head_invert_roll` |

**패널이 그리는 안내 문구**

* Drives Preset Sliders live - always follows
* whichever character slot is active.
* Stream
* Host
* Port
* Smoothing
* Deadzone
* Gain
* Apply error (see console for full trace):
* Head Rotation (Experimental)
* Drives the 'head' bone on that slot's
* Rigify_Ctrl_NN rig (Apply Retarget +
* Link Head Rig first).
* No Rigify control rig for this slot
* This rig has no 'head' bone to drive
* 'head' bone has a rotation axis LOCKED
* (Item tab > Transform > Rotation - unlock it)
* Head Rig not linked - click 'Link Head Rig' above
* Linked, but 'head' bone isn't in the retarget
* handler - try Unlink then Link Head Rig again
* Head Rig linked - ready
* No head rotation data in this stream
* Drives the Preset Sliders list (see
* Expression Presets) live - watch values
* update there while connected. The 52
* ARKit presets ship with MetaBridge.

---

## 4. Batch Tools

패널 키: `batch_tools`

폴더 전체에 의미 있는 두 가지 작업을 돌립니다. 모든 캐릭터 어셈블, 모든 슬롯 내보내기.

![Batch Tools](assets/panel_batch_tools.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Assemble All Characters | `mmb_batch_assemble` |
| Export All Slots | `mmb_batch_export` |

---

## 5. Body Blend (experimental)

패널 키: `body_blend`

여러 바디(DNA 파일 또는 라이브러리 아키타입)를 가중치로 평균해 새 캐릭터 하나를 만듭니다.

![Body Blend (experimental)](assets/panel_body_blend.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Use Base DNA | `mmb_add_base_dna` |
| Add Folder... | `mmb_add_body_folder` |
| Add Body DNA | `mmb_add_body_source` |
| Load Library... | `mmb_load_archetype_library` |
| Export... | `mmb_export_archetype_library` |
| Build Blended Body | `mmb_build_blended_body` |
| Blend Active Character | `mmb_blend_active_character` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Ml Body Blend Name | 텍스트 | `Blended_Body` | — | `ml_body_blend_name` |
| LOD | 숫자 | `0` | 0 – 7 | `ml_body_blend_lod` |
| Replace | 체크박스 | off | — | `ml_body_blend_replace` |
| Live Preview | 체크박스 | on | — | `ml_body_blend_live_preview` |

---

## 6. Send to Cascadeur

패널 키: `cascadeur`

캐릭터나 애니메이션을 localhost로 Cascadeur에 보내고, 이 리그를 Cascadeur 씬에 실시간으로 미러링합니다.

![Send to Cascadeur](assets/panel_cascadeur.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Send to Cascadeur | `mmb_cascadeur_send` |
| Current Frame | `mmb_cascadeur_send` |
| Live: Mirror This Rig | `mmb_cascadeur_live_pose` |
| Stop Mirroring | `mmb_cascadeur_stop_live` |
| Cascadeur Status | `mmb_cascadeur_status` |
| Install Cascadeur Plug-in | `mmb_install_cascadeur_plugin` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Send | 메뉴 | `CHARACTER` | CHARACTER = Character and Bones, KEYS = Keyframes Only | `ml_casc_mode` |
| Include Head | 체크박스 | on | — | `ml_casc_send_head` |
| Face Bones | 체크박스 | off | — | `ml_casc_face_bones` |
| Include Animation | 체크박스 | on | — | `ml_casc_send_anim` |
| Append | 체크박스 | off | — | `ml_casc_append` |
| Frame Rate | 숫자 | `30.0` | 1 – 240 | `ml_casc_fps` |
| Live | 메뉴 | `OUT` | OUT = Maya to Cascadeur, IN = Cascadeur to Maya, BOTH = Both Ways | `ml_casc_live_way` |
| Bones | 메뉴 | `ROLES` | ROLES = Mapped Bones, ALL = Whole Skeleton | `ml_casc_live_bones` |
| Port | 숫자 | — | 1024 – 65535 | `ml_casc_port` |

**패널이 그리는 안내 문구**

* Opens as a new scene in Cascadeur
* Overwrites from frame 0
* Send the character first, then Live.
* Run 'Animation Scripts > MetaBridge Live' in Cascadeur first

---

## 7. DNA Validation

패널 키: `validation`

DNA 파일 또는 활성 슬롯의 DNA를 읽고, 파이프라인의 나머지가 만나기 전에 무엇이 잘못됐는지 알려 줍니다.

![DNA Validation](assets/panel_validation.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Validate DNA File... | `mmb_validate_dna_file` |
| Validate Active Slot | `mmb_validate_active_slot` |

---

## 8. Export (DNA / FBX / glTF)

패널 키: `exporter`

활성 캐릭터를 내보냅니다. 머리와 몸을 DNA로, 캐릭터를 FBX로, 또는 glTF로.

![Export (DNA / FBX / glTF)](assets/panel_exporter.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Head | `mmb_export_head_dna` |
| Body | `mmb_export_body_dna` |
| Export FBX | `mmb_export_slot_fbx` |
| Export glTF | `mmb_export_slot_gltf` |

**패널이 그리는 안내 문구**

* DNA (.dna)
* FBX
* glTF

---

## 9. MD Live

패널 키: `md_live`

공유 폴더 하나를 통한 Marvelous Designer 왕복: 아바타가 나가고 의상이 돌아옵니다.

![MD Live](assets/panel_md_live.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Live | `mmb_md_live` |
| Get Garment Now | `mmb_md_request_garment` |
| Open Shared Folder | `mmb_md_open_folder` |
| Send Body to MD | `mmb_md_send_body` |
| Import Garment from MD... | `mmb_md_import_garment` |
| Open MD Plug-in Folder | `mmb_md_open_plugin_folder` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Wear As | 메뉴 | — | 실행 시 생성 | `ml_md_live_category` |
| MD Simulate Frames | 숫자 | `30` | 0 – 500 | `ml_md_sim_steps` |
| Auto-Return Garment | 체크박스 | — | — | `ml_md_auto_return` |
| Merge Pattern Pieces | 체크박스 | off | — | `ml_md_merge_pieces` |
| Shared Folder | 텍스트 | — | — | `ml_md_folder` |
| MD Scale | 숫자 | `1000.0` | 0.001 | `ml_md_scale` |
| Include Head | 체크박스 | on | — | `ml_md_send_head` |
| Prepare for Auto-Fit | 체크박스 | on | — | `ml_md_prepare_autofit` |
| Import Scale | 숫자 | `100.0` | 0.001 | `ml_md_import_scale` |

**패널이 그리는 안내 문구**

* MD: run maya_live from the Plug-in menu
* Shared Folder:
* Maya to Marvelous Designer
* Marvelous Designer to Maya
* large - stitches are left out while reading
* no garment from MD yet
* MD Plug-ins (one-time setup)
* In MD: Plug-in > Plug-in Manager > Add
* maya_live.py from this folder (Live),
* maya_load_avatar / maya_send_garment (one-shot)
* plug-in knows the latest avatar

---

## 10. Expression Presets

패널 키: `pose_presets`

표정 프리셋을 파일로. 얼굴 보드의 다이얼 값을 저장하고, 다시 적용하고, 여러 개를 슬라이더로 동시에 블렌딩합니다.

![Expression Presets](assets/panel_pose_presets.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Save Current Expression | `mmb_save_pose_preset_overwrite` |
| Save As Current Expression... | `mmb_save_pose_preset` |
| Delete Expression Preset | `mmb_delete_pose_preset` |
| Apply Preset | `mmb_apply_pose_preset` |
| Add All From Active Folder | `mmb_add_folder_sliders` |
| Clear All Sliders | `mmb_clear_preset_sliders` |
| Import... | `mmb_import_pose_preset` |
| Set Folder... | `mmb_select_preset_folder` |
| Open Presets Folder | `mmb_open_preset_folder` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Preset | 메뉴 | — | 실행 시 생성 | `ml_preset_enum` |

---

## 11. External Preset Converter

패널 키: `preset_converter`

다른 툴의 프리셋(마야·Houdini 프리셋, ARKit 페이로드)을 이름을 맞춰 보드 컨트롤로 가져옵니다.

![External Preset Converter](assets/panel_preset_converter.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Convert & Import (Maya/Houdini)... | `mmb_convert_import_preset` |
| Convert ARKit Payload... | `mmb_convert_arkit_payload` |
| Edit Name Mapping | `mmb_edit_name_mapping` |

**패널이 그리는 안내 문구**

* Fill empty targets, then re-import

---

## 12. Proportions

패널 키: `proportions`

바디 슬라이더. 다리·몸통·팔 길이, 어깨·허리·가슴 너비, 굽과 앞굽 높이. 슬라이더를 움직이면 캐릭터가 움직입니다.

![Proportions](assets/panel_proportions.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Long Legs | `mmb_proportion_preset` |
| Reset | `mmb_proportion_preset` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Leg Length | 숫자 | `1.0` | 0.8 – 1.3 | `leg` |
| Torso Length | 숫자 | `1.0` | 0.85 – 1.2 | `torso` |
| Neck Length | 숫자 | `1.0` | 0.8 – 1.3 | `neck` |
| Arm Length | 숫자 | `1.0` | 0.85 – 1.2 | `arm` |
| Shoulder Width | 숫자 | `1.0` | 0.85 – 1.2 | `shoulder` |
| Hip Width | 숫자 | `1.0` | 0.85 – 1.2 | `hip` |
| Waist | 숫자 | `1.0` | 0.75 – 1.3 | `waist` |
| Chest | 숫자 | `1.0` | 0.8 – 1.25 | `chest` |
| Hips | 숫자 | `1.0` | 0.8 – 1.25 | `hips` |
| Thigh | 숫자 | `1.0` | 0.75 – 1.3 | `thigh` |
| Calf | 숫자 | `1.0` | 0.75 – 1.3 | `calf` |
| Upper Arm | 숫자 | `1.0` | 0.75 – 1.3 | `upper_arm` |
| Forearm | 숫자 | `1.0` | 0.75 – 1.3 | `forearm` |
| Neck Thickness | 숫자 | `1.0` | 0.8 – 1.25 | `neck_girth` |
| Bust | 숫자 | `1.0` | 0.5 – 1.5 | `bust` |
| Head Size | 숫자 | `1.0` | 0.9 – 1.1 | `head` |
| Heel Height | 숫자 | `0.0` | 0 – 15 | `heel` |
| Front Height | 숫자 | `0.0` | 0 – 5 | `platform` |

**패널이 그리는 안내 문구**

* Assemble a character with a body first
* Remove the control rig first
* Build it again afterwards
* Bust needs the LOD 0 body

---

## 13. Pose Reset

패널 키: `pose_reset`

얼굴 보드를 중립으로 되돌립니다. 전부, 또는 선택한 컨트롤만.

![Pose Reset](assets/panel_pose_reset.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Reset All Controls | `mmb_reset_face_pose` |
| Reset Selected (Pose Mode) | `mmb_reset_selected_controls` |

---

## 14. Retarget Rigify Animation (Beta)

패널 키: `rig_retarget`

다른 리그(UE5, Mixamo, MetaHuman, Rigify)의 애니메이션을 이 캐릭터에, HumanIK에, 또는 mGear 리그에 리타겟합니다.

![Retarget Rigify Animation (Beta)](assets/panel_rig_retarget.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Retarget Rigify Animation | `mmb_retarget_rigify_animation` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Source Type | 메뉴 | `UE5` | 실행 시 생성 | `ml_retarget_source_type` |
| Source Rig | 노드 피커 | — | — | `ml_retarget_source_rig` |
| Target Rig | 노드 피커 | — | — | `ml_retarget_target_rig` |
| Quality | 메뉴 | `PRECISE` | 실행 시 생성 | `ml_retarget_quality` |

### Retarget in Maya (HumanIK / mGear)

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Retarget Onto | 메뉴 | `JOINTS` | JOINTS = Character Joints, HUMANIK = HumanIK (Maya), MGEAR = mGear Controls | `ml_retarget_target_mode` |
| Target Type | 메뉴 | `AUTO` | 실행 시 생성 | `ml_retarget_target_type` |
| Legs on IK | 체크박스 | on | — | `ml_retarget_legs_ik` |
| Source Rest Frame | 숫자 | `-1` | -1 – 1000 | `ml_retarget_rest_frame` |

---

## 15. Live Corrective Sculpting (Beta)

패널 키: `sculpt_correctives`

포즈를 잡은 채 피부를 조각하고, 그 차이를 이름 붙은 커렉티브로 저장하고, 입은 옷까지 동기화합니다.

![Live Corrective Sculpting (Beta)](assets/panel_sculpt_correctives.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Begin (Face) | `mmb_sculpt_corrective_begin` |
| Begin (Body) | `mmb_sculpt_corrective_begin` |
| Finish Sculpt | `mmb_sculpt_corrective_finish` |
| Export Edited Shape Keys | `mmb_export_edited_shape_keys` |
| Bake All to DNA | `mmb_bake_all_correctives_to_dna` |
| Export... | `mmb_export_correctives` |
| Import... | `mmb_import_correctives` |
| Sync to Wearables | `mmb_sync_correctives_to_garments` |
| Set Neutral | `mmb_sculpt_corrective_set_neutral` |
| Toggle Manual Override | `mmb_sculpt_corrective_toggle_manual` |
| Remove Corrective | `mmb_sculpt_corrective_remove` |
| Edit Sculpt | `mmb_sculpt_corrective_edit` |
| Bake Corrective to DNA | `mmb_bake_corrective_to_dna` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Corrective | 텍스트 | — | — | `ml_lcs_name` |
| Head Driver Bone | 텍스트 | — | — | `ml_lcs_head_bone` |
| Body Driver Bone | 메뉴 | — | 실행 시 생성 | `ml_lcs_body_bone` |
| Value | 숫자 | `1.0` | 0 – 1 | `value` |

**패널이 그리는 안내 문구**

* Name is required for both Face and Body below
* No bone with that name on the head armature
* No body armature in the active character
* Body correctives not registered - Apply Retarget on the body first
* No bone with that name on the body armature
* Write to DNA (head only)
* Sculpt a DNA key (e.g. jaw_open), then this replaces that channel
* ⇱ on a face shape key row assigns its channel

---

## 16. Unreal Live

패널 키: `unreal_live`

작업하는 동안 얼굴을 언리얼 엔진으로 스트리밍해, 그쪽 MetaHuman이 이 캐릭터와 함께 연기하게 합니다.

![Unreal Live](assets/panel_unreal_live.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Start Unreal Live | `mmb_unreal_live_start` |
| Stop Unreal Live | `mmb_unreal_live_stop` |
| Open Unreal Plug-in Folder | `mmb_open_unreal_plugin_folder` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Port | 숫자 | — | 1024 – 65535 | `ml_unreal_live_port` |
| Rate | 숫자 | `30` | 1 – 120 | `ml_unreal_live_fps` |
| Mirror | 메뉴 | `Y` | NONE = None, X = Flip X, Y = Flip Y, Z = Flip Z | `ml_unreal_live_mirror` |

**패널이 그리는 안내 문구**

* Load a character first
* Add a MotionForge source in Unreal's Live Link window

---

## 17. Follow Unreal

패널 키: `unreal_follow`

반대 방향. 언리얼이 애니메이팅하는 MetaHuman을 이 캐릭터가 따라갑니다.

![Follow Unreal](assets/panel_unreal_follow.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Follow Unreal | `mmb_unreal_follow_start` |
| Stop Following | `mmb_unreal_follow_stop` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Host | 텍스트 | `127.0.0.1` | — | `ml_unreal_follow_host` |
| Port | 숫자 | — | 1024 – 65535 | `ml_unreal_follow_port` |
| Apply Rate | 숫자 | `15` | 1 – 60 | `ml_unreal_follow_rate` |
| Body | 체크박스 | on | — | `ml_unreal_follow_body` |
| Face | 체크박스 | on | — | `ml_unreal_follow_face` |

**패널이 그리는 안내 문구**

* Run MotionForge.Send.Start in Unreal
* Rigify is stood down while following

---

## 18. Wearables (experimental)

패널 키: `wearables`

캐릭터 위의 의상·헤어·액세서리. 가져오기, 의상 리그 만들기, 바인딩, 그리고 바디가 바뀌면 다시 피팅.

![Wearables (experimental)](assets/panel_wearables.png)

### 패널 위쪽

**버튼**

| 버튼 | 실행되는 커맨드 |
| --- | --- |
| Import Clothing (FBX)... | `mmb_import_clothing_fbx` |
| Head Accessory... | `mmb_import_clothing_fbx` |
| Refit Clothing To Body | `mmb_refit_wearables` |
| Make Garment Rig | `mmb_make_garment_rig` |
| Bind Garment To Character | `mmb_bind_garment` |
| Import Hair... | `mmb_import_hair_abc` |
| Apply Hair Offset / Scale | `mmb_apply_hair_offset` |
| Bind Hair To Head | `mmb_bind_hair_to_head` |
| Align Active Mesh to DNA Head | `mmb_align_mesh_to_dna_head` |
| Retarget Hair to Selected Mesh | `mmb_retarget_hair` |

**설정**

| 컨트롤 | 종류 | 기본값 | 범위 | 저장 위치 |
| --- | --- | --- | --- | --- |
| Clothing Offset | 숫자 | — | 0 – 0.02 | `ml_wearable_fit_margin` |
| Import | 메뉴 | `ALL` | ALL = Guides + Strands, STRANDS = Strands only, GUIDES = Guides only | `ml_hair_kind` |
| Hair Strands (0 = all) | 숫자 | `10000` | 0 – 400000 | `ml_hair_max_strands` |
| Hair Offset X | 숫자 | `0.0` | -100 – 100 | `ml_hair_offset_x` |
| Hair Offset Y | 숫자 | `0.0` | -100 – 100 | `ml_hair_offset_y` |
| Hair Offset Z | 숫자 | `0.0` | -100 – 100 | `ml_hair_offset_z` |
| Hair Scale | 숫자 | `1.0` | 0.1 – 3 | `ml_hair_scale` |

**패널이 그리는 안내 문구**

* No active character - Assemble or Build one first
* Clothing (FBX):
* Scene Mesh Garment:
* Hair (Alembic -> XGen groom):

---

[가이드로 돌아가기](KO_index.md)
