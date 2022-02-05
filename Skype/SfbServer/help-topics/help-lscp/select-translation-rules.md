---
title: Auswählen von Übersetzungsregeln
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 'Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das E.164-Format normalisiert werden, um eine umgekehrte Nummernsuche (Reverse Number Lookup, RNL) durchzuführen. Der Trunkpeer (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie optional eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.'
---

# <a name="select-translation-rules"></a>Auswählen von Übersetzungsregeln
 
 Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das E.164-Format normalisiert werden, um eine umgekehrte Nummernsuche (Reverse Number Lookup, RNL) durchzuführen. Der Trunkpeer (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie optional eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
  
> [!IMPORTANT]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine Alternative zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten. 
  
Klicken Sie auf eine Regel in der Liste und anschließend auf **OK**, um eine vorhandene Übersetzungsregel zu verwenden.
  
Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server Systemsteuerung ausführen können, finden Sie unter [Verwalten Skype for Business Server 2015](../../manage/manage.md).
  

