# waves over lambda - Points: 300

## Problem

We made alot of substitutions to encrypt this. Can you decrypt it? Connect with ```nc 2019shell1.picoctf.com 21903```.

## Hints

> Flag is not in the usual flag format

## Overview

In this challenge, we are given the another pair of domain and port.
```
2019shell1.picoctf.com 21903
```
Once again let's try connecting to it via TCP.
```
$ nc 2019shell1.picoctf.com 21903
-------------------------------------------------------------------------------
lfsaowjd cxox pd rfko miwa - moxekxslr_pd_l_ftxo_iwuqyw_tiscswddju
-------------------------------------------------------------------------------
qxjhxxs kd jcxox hwd, wd p cwtx wioxwyr dwpy dfuxhcxox, jcx qfsy fm jcx dxw. qxdpyxd cfiypsa fko cxwojd jfaxjcxo jcofkac ifsa zxopfyd fm dxzwowjpfs, pj cwy jcx xmmxlj fm uwbpsa kd jfixowsj fm xwlc fjcxo'd rwosdwsy xtxs lfstpljpfsd. jcx iwhrxojcx qxdj fm fiy mxiifhdcwy, qxlwkdx fm cpd uwsr rxwod wsy uwsr tpojkxd, jcx fsir lkdcpfs fs yxlb, wsy hwd irpsa fs jcx fsir oka. jcx wllfksjwsj cwy qofkacj fkj wioxwyr w qfn fm yfupsfxd, wsy hwd jfrpsa wolcpjxljkowiir hpjc jcx qfsxd. uwoifh dwj lofdd-ixaaxy opacj wmj, ixwspsa wawpsdj jcx upvvxs-uwdj. cx cwy dksbxs lcxxbd, w rxiifh lfuzixnpfs, w djowpacj qwlb, ws wdlxjpl wdzxlj, wsy, hpjc cpd woud yofzzxy, jcx zwiud fm cwsyd fkjhwoyd, oxdxuqixy ws pyfi. jcx ypoxljfo, dwjpdmpxy jcx wslcfo cwy affy cfiy, uwyx cpd hwr wmj wsy dwj yfhs wufsadj kd. hx xnlcwsaxy w mxh hfoyd iwvpir. wmjxohwoyd jcxox hwd dpixslx fs qfwoy jcx rwlcj. mfo dfux oxwdfs fo fjcxo hx ypy sfj qxaps jcwj awux fm yfupsfxd. hx mxij uxypjwjptx, wsy mpj mfo sfjcpsa qkj ziwlpy djwopsa. jcx ywr hwd xsypsa ps w dxoxspjr fm djpii wsy xnekpdpjx qopiipwslx. jcx hwjxo dcfsx zwlpmplwiir; jcx dbr, hpjcfkj w dzxlb, hwd w qxspas puuxsdpjr fm ksdjwpsxy ipacj; jcx txor updj fs jcx xddxn uwodc hwd ipbx w awkvr wsy owypwsj mwqopl, cksa mofu jcx hffyxy opdxd psiwsy, wsy yowzpsa jcx ifh dcfoxd ps ypwzcwsfkd mfiyd. fsir jcx aiffu jf jcx hxdj, qoffypsa ftxo jcx kzzxo oxwlcxd, qxlwux ufox dfuqox xtxor upskjx, wd pm wsaxoxy qr jcx wzzofwlc fm jcx dks.
```
There's a bunch of weird ass characters. This is supposed to be another substitutions cipher challenge. 

## Solutions

Looking at these characters, I was pretty sure these couldn't be any common substitution cipher such as Caesar or Vinegere like on the other challenges. These are just messed up and not in any kind of particular order.

Since the character seems to have been replaced with one another, I made an analysis on the site called [quipqiup](https://quipqiup.com/).

This looks like a decent result
```
congrats here is your flag - frequency_is_c_over_lambda_vlnhnasstm ------------------------------------------------------------------------------- between us there was, as i have already said somewhere, the bond of the sea. besides holding our hearts together through long periods of separation, it had the effect of ma?ing us tolerant of each other's yarnsand even convictions. the lawyerthe best of old fellowshad, because of his many years and many virtues, the only cushion on dec?, and was lying on the only rug. the accountant had brought out already a box of dominoes, and was toying architecturally with the bones. marlow sat cross-legged right aft, leaning against the mi??en-mast. he had sun?en chee?s, a yellow complexion, a straight bac?, an ascetic aspect, and, with his arms dropped, the palms of hands outwards, resembled an idol. the director, satisfied the anchor had good hold, made his way aft and sat down amongst us. we exchanged a few words la?ily. afterwards there was silence on board the yacht. for some reason or other we did not begin that game of dominoes. we felt meditative, and fit for nothing but placid staring. the day was ending in a serenity of still and exquisite brilliance. the water shone pacifically; the s?y, without a spec?, was a benign immensity of unstained light; the very mist on the essex marsh was li?e a gau?y and radiant fabric, hung from the wooded rises inland, and draping the low shores in diaphanous folds. only the gloom to the west, brooding over the upper reaches, became more sombre every minute, as if angered by the approach of the sun.
```

So, the flag should be:
```
picoCTF{frequency_is_c_over_lambda_vlnhnasstm}
```
