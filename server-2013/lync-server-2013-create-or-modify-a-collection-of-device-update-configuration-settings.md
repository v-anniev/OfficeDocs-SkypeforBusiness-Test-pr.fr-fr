﻿---
title: Créer ou modifier une collection de paramètres de configuration de la mise à jour des périphériques
TOCTitle: Créer ou modifier une collection de paramètres de configuration de la mise à jour des périphériques
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994029(v=OCS.15)
ms:contentKeyID: 53095396
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une collection de paramètres de configuration de la mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les paramètres de configuration de mise à jour des périphériques peuvent être créés (au niveau de l’étendue Site) à l’aide de Windows PowerShell et de l’applet de commande **New-CsDeviceUpdateConfiguration** et modifiés à l’aide de l’applet de commande **Set-CsDeviceUpdateConfiguration**. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398920.note(OCS.15).gif" title="note" alt="note" />Remarque :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.</td>
</tr>
</tbody>
</table>



## Pour créer des paramètres de configuration de mise à jour des périphériques qui utilisent les valeurs par défaut

  - Cette commande crée un ensemble de paramètres de configuration de mise à jour des périphériques pour le site de Redmond :
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Comme aucun paramètre autre que celui obligatoire sur l’identité n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.

## Pour modifier une seule valeur de propriété lors de la création de paramètres de configuration de mise à jour des périphériques

  - Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de mise à jour des périphériques qui, par défaut, supprime les anciens fichiers journaux tous les 21 jours, utilisez une commande comme celle-ci :
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

## Pour modifier plusieurs valeurs de propriété lors de la création de paramètres de configuration de mise à jour des périphériques

  - Il est possible de modifier plusieurs valeurs de propriété en incluant plusieurs paramètres. Par exemple, cette commande définit l’intervalle de nettoyage des journaux sur 21 jours et l’intervalle de vidage des journaux sur 30 minutes :
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

Pour plus d’informations sur la modification des paramètres de configuration des périphériques existants, voir la rubrique d’aide relative à l’applet de commande [Set-CsDeviceUpdateConfiguration](set-csdeviceupdateconfiguration.md). Pour plus d’informations sur la création de collections de paramètres de configuration, voir la rubrique d’aide relative à l’applet de commande [New-CsDeviceUpdateConfiguration](new-csdeviceupdateconfiguration.md).
