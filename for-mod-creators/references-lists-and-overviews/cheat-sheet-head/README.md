# Cheat Sheet: Head

#### Summary

**Last documented edit**: January 14 2024 by [manavortex](https://app.gitbook.com/u/NfZBoxGegfUqB33J9HXuCs6PVaC3 "mention")

This page lists various properties of the player head. Use the Table of Contents or your browser's search (Hotkey: `Ctrl+F`) to quickly find what you're looking for.&#x20;

{% hint style="info" %}
You can find much additional information about the player head under [npv-preparing-the-head-in-blender.md](../../modding-guides/npcs/npv-v-as-custom-npc/npv-preparing-the-head-in-blender.md "mention")&#x20;
{% endhint %}

### Wait, this isn't what I'm looking for!

* If you want to [edit the player's head](../../modding-guides/npcs/a-new-head-for-v.md), you need [meshes](../../files-and-what-they-do/3d-objects-.mesh-files/) and [morphtargets](../../3d-modelling/morphtargets.md).&#x20;
* If you want to make a custom NPC, check [npv-v-as-custom-npc](../../modding-guides/npcs/npv-v-as-custom-npc/ "mention")

***

## Head file paths

<table data-header-hidden><thead><tr><th width="166.33333333333331">Body gender</th><th width="166">file extension</th><th>file path</th></tr></thead><tbody><tr><td>female</td><td><code>.mesh</code></td><td><code>base\characters\head\player_base_heads\player_female_average\h0_000_pwa_c__basehead\</code></td></tr><tr><td>female</td><td><code>.morphtarget</code></td><td><code>base\characters\head\player_base_heads\player_female_average</code></td></tr><tr><td>male</td><td><code>.mesh</code></td><td><code>base\characters\head\player_base_heads\player_man_average\h0_000_pwa_c__basehead\</code></td></tr><tr><td>male</td><td><code>.morphtarget</code></td><td><code>base\characters\head\player_base_heads\player_man_average</code></td></tr></tbody></table>

{% hint style="info" %}
The folders contain the entire player head. The minimum amount of meshes rendered is 3 (head, teeth, eyes), and can go up to 13 (fem V)/14 (masc V).&#x20;
{% endhint %}

### Head file prefixes

|       |                                                                                                                                         |
| ----- | --------------------------------------------------------------------------------------------------------------------------------------- |
| h0\_  | head (with ears)                                                                                                                        |
| hb\_  | male V only: beard                                                                                                                      |
| heb\_ | eyebrows                                                                                                                                |
| he\_  | eyes                                                                                                                                    |
| ht\_  | teeth                                                                                                                                   |
| hx\_  | <p>applied on top of h0: </p><ul><li>cyberware</li><li>makeup</li><li>freckles</li><li>pimples</li><li>tattoos</li><li>scars </li></ul> |
| l1\_  | ear ring (01-04)                                                                                                                        |

## Skin tones by index

<table><thead><tr><th width="85"></th><th></th></tr></thead><tbody><tr><td>1</td><td>01_ca_pale</td></tr><tr><td>2</td><td>01_ca_pale_00_warm_ivory</td></tr><tr><td>3</td><td>02_ca_limestone</td></tr><tr><td>4</td><td>02_ca_limestone_00_beige</td></tr><tr><td>5</td><td>03_ca_senna</td></tr><tr><td>6</td><td>03_ca_senna_00_amber</td></tr><tr><td>7</td><td>03_ca_senna_01_honey</td></tr><tr><td>8</td><td>03_ca_senna_02_band</td></tr><tr><td>9</td><td>04_ca_almond</td></tr><tr><td>10</td><td>04_ca_almond_00_umber</td></tr><tr><td>11</td><td>05_bl_espresso</td></tr><tr><td>12</td><td>06_bl_dark</td></tr></tbody></table>

List compiled by **wolv**

## Complexions

Every complexion has its own associated texture file. These are sorted by body gender under

```
base\characters\head\wa\h0_001_wa_c__basehead\textures\h0_000_wa_c__basehead_d0X.xbm
base\characters\head\ma\h0_001_ma_c__basehead\textures\h0_000_ma_c__basehead_d0X.xbm
```

The files are ending in `01..05`. Each complexion has its own appearance in the head mesh, e.g.:&#x20;

```
03_ca_senna
03_ca_senna_d02
03_ca_senna_d03
03_ca_senna_d04
03_ca_senna_d05
```

## Skin definitions

Skin materials are defined in the base head file:&#x20;

<table><thead><tr><th width="251"></th><th></th></tr></thead><tbody><tr><td>female body gender</td><td><code>base\characters\head\player_base_heads\player_female_average\h0_000_pwa_c__basehead\h0_000_pwa_c__basehead.mesh</code></td></tr><tr><td>male body gender</td><td><code>base\characters\head\player_base_heads\player_man_average\h0_000_pma_c__basehead\h0_000_pma_c__basehead.mesh</code></td></tr></tbody></table>

You can find the [definitions](../../files-and-what-they-do/3d-objects-.mesh-files/#step-3-material-definition) in the localMaterialBuffer. Each material overrides the following [properties](../../materials/configuring-materials/#checking-material-properties) locally:

* Normal (bump/height map)
* Albedo (diffuse/complexion)

All other properties are pulled from a [.mi file](../../files-and-what-they-do/materials/re-using-materials-.mi.md) in the following folder:

<table><thead><tr><th width="251"></th><th></th></tr></thead><tbody><tr><td>female body gender</td><td><code>base\characters\common\skin\character_mat_instance\female\head\</code></td></tr><tr><td>male body gender</td><td><code>base\characters\common\skin\character_mat_instance\male\head\</code></td></tr></tbody></table>

### Head: material instances

This section only lists [.mi files](../../files-and-what-they-do/materials/re-using-materials-.mi.md) used by the player head.&#x20;

{% hint style="warning" %}
About half of these files are shared by NPCs. Editing or replacing these will affect all of Night City!
{% endhint %}

<table><thead><tr><th width="550">File name (use male_head for masc)</th><th>Shared with NPCs</th></tr></thead><tbody><tr><td><code>female_head_01_ca_pale_00_warm_ivory.mi</code></td><td>❌</td></tr><tr><td><code>female_head_01_ca_pale.mi</code></td><td>✔</td></tr><tr><td><code>female_head_02_ca_limestone_00_beige.mi</code></td><td>❌</td></tr><tr><td><code>female_head_02_ca_limestone.mi</code></td><td>✔</td></tr><tr><td><code>female_head_03_ca_senna_00_amber.mi</code></td><td>❌</td></tr><tr><td><code>female_head_03_ca_senna_01_honey.mi</code></td><td>❌</td></tr><tr><td><code>female_head_03_ca_senna_02_band.mi</code></td><td>❌</td></tr><tr><td><code>female_head_03_ca_senna.mi</code></td><td>✔</td></tr><tr><td><code>female_head_04_ca_almond_00_umber.mi</code></td><td>❌</td></tr><tr><td><code>female_head_04_ca_almond.mi</code></td><td>✔</td></tr><tr><td><code>female_head_05_bl_espresso.mi</code></td><td>✔</td></tr><tr><td><code>female_head_06_bl_dark.mi</code></td><td>✔</td></tr></tbody></table>

## **Freckles / cheek make-up**

For a list of freckles and make-up sorted by colour and skin type, see NoraLee's [NPV guide](https://docs.google.com/document/d/1clFJhpi7H5jk73vUQPnjIwjkuQV6VnYkKMoXt1eYMb0/edit#bookmark=id.lau0nfbbx4id).

## Lipstick

{% hint style="info" %}
For a mod fixing various mix-ups in the character creator, see [here](https://www.nexusmods.com/cyberpunk2077/mods/6788).
{% endhint %}

Lipstick colours and styles are sorted in (more or less) ascending order in the appearance list in the mesh.&#x20;

Style order is Default - Glossy - Matte (no suffix, \_02_, \__03)

Link: [Reference images on imgur](https://imgur.com/a/NlbCHYK)

<figure><img src="https://i.imgur.com/P5NMggv.png" alt=""><figcaption></figcaption></figure>

## Eyeliner and kohl

{% hint style="info" %}
To be done. Are you bored (and potentially have OCD)? Please get in touch via Discord!
{% endhint %}

