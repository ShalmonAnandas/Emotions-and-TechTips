---
layout: post
title: Git + Github for Beginners
categories: Tutorial
author: "Shalmon Anandas"
tags: [Github, Git, Tutorial]
---

Github was the first thing I had to learn to make my life easier when I started programming. Github quantifies how productive I am (which isnt a lot) by giving me graphs of how much shit I got done in that day, and in my opinion, thats priceless. Version control and having copies of all the code youve written as it is on multiple computers is also good I guess. But the graphs??!! Thats some gourmet shit. *chefs kiss*

I'll walk you through the installation (on Windows [Linux coming soon]), the basic commands and some good practices to get you started with Git and Github.

The goal of this post is cause when I was starting out to learn git as well as github. There were no good, comprehensive, mordern, written resources to learn. I had to rely on bits and pieces of youtube videos and googling to get myself started. Hopefully, This is a comprehensive well rounded guide to git and github.

## STEP 1 : MAKE AN ACCOUNT
![make-an-account-ss](https://i.imgur.com/eFplu6R.png)

Just do it. Make an account. And then we'll move ahead.

## STEP 2 : INSTALL GIT
Visit the [Git](https://git-scm.com/download/win) homepage and download the exe suitable for your computer. Usually 64bit will be the right one, but if you still insist on checking you can search for "system information" in the start menu and check in there.

![system-information](https://i.imgur.com/TYanuxg.png)

The installation is pretty straight-forward but I'll still walk you through using screenshots and try to explain each and every option as simply as I can.

![git-install-1](https://i.imgur.com/jNpzVgE.png)

Just go next here. You can read the license if you want. But bruh, who does that, amirite? (I do that, GPL licenses are pretty fun to read. Give it a try sometime)

![git-install-2](https://i.imgur.com/J4qqZ0R.png)
Go next here as well. This is important if you want to do a custom install on a different drive. I'm not sure why you would do that but there must be a reason why this is here.

![git-install-3](https://i.imgur.com/eObW4Ze.png)
Go next here as well. I'll explain all the options though (Skip reading this if not interested). By default git installs a pretty good combination of components.

1. By default it doesn't make a desktop icon. Which is a good thing because it isnt necessary. Normally you will use git from inside a directory.
2. "Windows Explorer integration" this is to add "Git bash here" and "GIt GUI here" options to the right-click menu while in windows explorer
3. "Git LFS" as it mentions is "LARGE FILE SUPPORT". This is an option if you want your repo to have files larger than 50mb in size. Which isn't that uncommon. So its a good thing that this is installed by default.
4. "Associate .git* files with default text editor" just opens the git config files in the text editor of your choice (which we will be choosing later). This is another quality of life feature
5. "Associate .sh files to be run with Bash" this is also a quality of life feature since .sh files are normally bash scripts so makes sense that it uses bash to run them.
6. "Check for daily updates" this is diabled by default since updating a piece of software in a production environment can sometime lead to the pipeline breaking, and thats a no-no we dont want that ever to happen. You can enable it if you want since it wont affect our use-case much but I'll personally leave it off.
7. "Add Git Bash profile to windows terminal" as it says adds the git bash option to your windows terminal. Its off by default since not most people have windows terminal installed and most of the git commands work without having to open git bash.

![git-install-4](https://i.imgur.com/gRWeW7v.png)
Go next here as well. 

This option is there in case you wanna change the name of the start menu folder. I don't know why you would do that either. Maybe incase you are installing multiple versions of git and want to differentiate between them? I don't even know if git allows that. I'm talking out of my ass rn.

![git-install-5](https://i.imgur.com/lCFP81U.png)
Here is the first part where we change something. This option changes the default editor for git. This is in case you want to write a big changelog in the commit or wanna edit something and using the command line will be hassle, its for those edge-cases.

By default it is set to "Use vim". We'll change it to "Use notepad"

![git-install-6](https://i.imgur.com/4rFFgRB.png)
We are gonna leave this on default and go next.

This option is there for when you work for a company or for an existing project where their github repository doesnt use the default "master" branch name. You can set the custom branch name here. But I like to leave this on default and then change the branch name while pushing (in the commandline) to github on a project to project basis if necessary.

![git-install-7](https://i.imgur.com/Uh6jk2j.png)
We are gonna leave this at default as well.

1. The first option enforces git commands to be used via only "git bash". We dont want that because we will be using windows terminal later on to learn how to actually use git.
2. This is the default option. This enables git to be used from any commandline emulator that is installed on your computer. This is the way to go.
3. This option install unix tools. Which im assuming is unix commands like find and sort like mentioned and overwrites the default windows definitions of these commands. But we dont want that. We dont wanna mess with default windows tools.

![git-install-8](https://i.imgur.com/kSEaqS4.png)
GO NEXT

This option lets us choose which ssh executable git uses with pushing and pull from repositories. Using the default bundled OpenSSH is fine. It wont affect us.
I'm guessing the other option is for workplaces where the git repo is only accessible via a certain proxy???

![git-install-9](https://i.imgur.com/djH7ydA.png)
GO NEXT AGAIN

This option lets you choose if you wanna use the default OpenSSL library for the HTTPS certificates while accessing github.
The other option, I'm guessing, is also for workplaces where they have their custom certificates to access the repository.

![git-install-10](https://i.imgur.com/FSq1g8C.png)
GO NEXT LMAO

This is to set the commit style. I don't understand this option even a little bit. I'll add more reading resources at the bottom so you can read up more about this.

![git-install-11](https://i.imgur.com/NHI61yM.png)
GO NEXT

This option doesnt make a difference. Its personal preference as far as I know. This setting specifies if the "Git Bash" opens in its own terminal emulator (MinTTY) by default or in windows command prompt.

Select whichever you want. Wont make much difference as far as I'm concerned.

![git-install-12](https://i.imgur.com/TxTTRcT.png)
GO NEXT

This specifies what the "git pull" command does by default. This comes into play when you are playing with multiple branches and stuff. The scope of this is to just set git up and get you going. I'll add further reading material at the bottom.

![git-install-13](https://lh3.googleusercontent.com/3bPVMmgxxiiAB9VcNO78ggI7sOdjbsiXKOaoCMCu7c9iHpWh6Z9MtOIxk42vEwHWe52k4Hf2B9M2kmxwNjAsOPGPbZ9VPdVKsdeVGSpNLRZTvcHcjrG_f8WOXrEoBCz-EMR3dOMB-iEiJUPRHx2vTGBBaljRccmAlawTnfVLbqRQAqbehR-Dd-ZgRbN4Hm5055hRFHWP46-dTk4RmCzOJUd15a6oRjVyWxIK-BQsSjVakBsD7RE8pg-6-PvsMAgL2q_jXwgTd-_YCM4W6IA-Sfd6MucXtdFfFI0KUHVpcLPOs3iaE5RcSp3pUfHav5cpS78NZFY927D1Z_SLSPRlFkygH31h3WuukVpx2svSN1VUcapmbARWH4Nm15cpImhjBZyZeNVaXLtb820xQ91J1u3gyyX1YqNbBg3o1QUjGNiyW_riO0Cpi8F1sGl4Ve9D4a9R0OsfgI2ZNmCuujVNkrM1CQrexuR0b_WAUp9UWL79jV3tJxLBi4_Wq2Qy_3JHPbfYpguDuTbEb8hhKuaegNGXFXFLiGiOEaFMQBXHMoiiViUix-iyei0THTtPfXq_W433HHbwtW6pzAe99RjUcYjO8gXQ34bz_gzltds6T_b0de8CqkgtMWrawvOi1q8LK0xkDsSlm-zwLGkKT5U5roeTDZZ5-BIHTbzSxdUQTN5Hmo14qIkDg8Dax0u9g3R9M8xuQHH6EeqwjncOV5lzuxQvcz1pTHIgWkTZQtWACjTrBjkp10qMLE9vi9yvxISL5bqOeUMbdtqtv6gAtAEDv4cyQhybvkhBVA=w513-h409-no?authuser=0)
GO NEXT

This is to select if you wanna use git credential manager to manage your git accounts or not. Leave this at default and go next

![git-install-14](https://lh3.googleusercontent.com/IpVt3O6CsCkRDMMfcU_iGVN55QvMKdJ1AiOVEfLarCC3AQejiSxqHxTypX2VibO9iR8_CHmXgs7V2FDhDbEjMXBX1w-BWsnWfV9VRKLTaQZlC_nYz1nlBKef6i8NnxRp6jOzioXoJD642P-G7tELIBvbo5qrz9SE9EwCs8zZGmWlW32eiOFL3PA1pUM7QBAnPYSzu66mztqRLvxDutHzeVUuotqlGFNupVBzcvd1dB6384Dxyv-giyHZdNI-UTmYaD2ws9RV3Fy5DidooHoYbg0LTtVjSg6oKu2wdBWkRqKoZhMTIqjoa5KLL3odVo5d156_qs-Fff5OEaydie8o5mI6Isnpv8N5guf_I3slErB4OAMx4ZNEUPiRQzAQAITEjedpbYbLeSqwHmsFkpnOZzchokScImce012WnqrQ91NkTVV0MuSkFtOyL_FZk1wfqm4kVv0HQENbzvT7Oanqmk_m5Im0gbSlR5S78ieF7vpk3qDFRft8YI7LJJt6yif6cDWswrzvI97bwQPFBei_s1BJJSPUfH-qXmupcolK7QEzS2xyc7pEnfLcKvZRXgomZUyJ-XOjXc5uypUQ6JV7H-ac9tzWC1qgOj3hm0Qj4RW2voKI4rz1GsrEiHKtRg9hel0o4OvrHRdC0RHXncpbpdHxaGgD8PYYcrLtehqZKBDv7VUXapWzMh1nKOP8WXgz_xv-AOnJgUZvtv9a_4sRU5WiddEE5QyZPRcCSWu-xJFv-vLHey8Yj2OTBnoouSYHvmdIGrA_g5AQNCwl-bNQUiILRPMcnBFQ4Q=w508-h402-no?authuser=0)
GO NEXT

There are two options here. TO enable file system caching and to enable symbolic links. I don't understand either. Look at the bottom of the post.

![git-install-15](https://lh3.googleusercontent.com/jKlHJQEK0rX_4P2X2GJJTb-4dLKLW1X4FvKz9nWsgnxeZXpjVzoHWkKsur2H1fOkptHSRl6cz3AU3opNpsSk3kGqUcBtwIu4Nlb5ddfxRZqcYzz02SD_Gh-HFs1LS-LNMFoa5L3ST-up9gMsZ4gdtcYJctEVpvYnbMn3148fhB0whTTLvhEOCLlvh-6Z518hP9AExggnxMDQqJysLCEdA66r6tIyi9nbGnaiAO0n-DVpVIiZ5a_dIb1EnYjG7hi7dVnrCEfvWBV6qQNXi1MwlJIlrYjxIeArOEC8l2SCEni4-Tt0McHhLiEsDR5Dza9YEf0QyglaahuMF5poPQEHi0qrWUdOOUpwaImeGOYA9E3MWjRuFEmeyGuPCrM0RyEtSyhAuoZyIrERfwwDSJnQFedw-AO1X64fdPfw6EEjU6WaGcAWGzAtuJbnYXgKQF7QopVtjK0loTKBNuGtyLOs18A6e_xTU45bMDSe62UgylBrhkZcoRtaHTi_Dt94FHbiI2NUU8KrwhZiwJizDdWw7MIXecIzMLfHMjLDN18tDt80M_hyDw6tSd0jNx5Y_wYwvUREMEbncNEe11zBt8A2QI4He-fZVkw_yKx3qxHDHreaY-kGkUbEgKn9V2_LMp7xw5gEGS9etE4SlrFG4K2Zq_kM4ZdK1FMcXQs0WytwCAgeHHClRtqjSXWdkdHZzUNSVco6HytsqIk2Bck6ez1-OXI819DpxRmMyBNsiMqmwG5egUMGhnTs3ilYQ2Q3njtQWjAXb8M4E0hN9p6x92hia4bomtyvRXsqlg=w509-h403-no?authuser=0)
GO NEXT

This lets you choose if you want experimental features. 
1. This option adds support to run console programs written using node or python natively in git bash.
2. This adds a feature where git will automatically keep running the common git commands to keep your repository up to date. 

We leave these off because I'm scared of messing with git. Git issues are solvable but are an inconviniece. When its the end of the day, you just wanna commit, git breaking itself or breaking your repository is the last thing you want to happen.

![git-install-16](https://lh3.googleusercontent.com/2NdldfOMk42m8e0GnYR25H5e3p3Y1cA6jmiGrRdb2gHa9CTvnzNs5B6RjjE7YUC-65dfSshbGSIDzA57R9ImzXyXUQ-QVrVEr_BZuFlU18ItQbOyzwVujVxNxVwKpF2pfvAXR6gLtcJIhiQkb4odfO5o66-OZlHsk2U2EpARsqmCk0Or-xmp7cLb_G2ALesJ4KWU42BobZZJQgNlkzvRZVihRfW73nERChGloWxoONZYnaJv9p0Wyi6OxE2rZCfd30Klz0xi2HzfApaGSpGWa0QljUHwjV8IKtL1kCUSWHX52EWl0A-yftdc54cLePnLPTekfNK_PczIPBAU_3VYFszedvhZHM69K8C_nrlLDg_okjSWDrDhR4KCOs0rkibRnWauNfaDO-hd7Bq6EUq6wBfxBUJdewAsRpSvunz0ozf2onqWSANCTfdB02tE2AsDlVpmf1gAh6_AR6B41crLXaYWINobekGdzjnDwGErs7Z6kjatxylsFV2jxTvQTR3JgaWaedeWQyt-2JTXVhFe8nGxT-F-7K4YtykCfQNY_zQ5svok_RtUA_-Qv4JFk0fYR-TF5cj1aMy96eki1_YAg-vpuOuS5cnZxfXV67CGDPbTLAOABTClT2U_--o2HBo4I4xvkn1RUvs85r1zVnQsdcDxw44hAZx7XcyMY5smdrONNP_WvHm4nOxe9Isyiq4Cc_Mx8GTeF11tz6CEWC6rR8OCs060biEeaHJoJ9GYIwYsVvQYruDKTe-5k1TqYjgvSKtfBuVqLe24Ma6hKaHu754ua-zAQFsD6g=w512-h404-no?authuser=0)
AND THATS IT.

You have successfully installed github and now know what the options do. More or less.

## Step 3 : INSTALL WINDOWS TERMINAL

This isnt a necessity. But I will show the next steps using this and it makes doing git stuff so muh easier.

You can install this from the [microsoft store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab)

![windows_terminal_store_page](https://i.imgur.com/islYa6z.png)

## STEP 4 : INITIALIZE GIT

Git when freshly installed, requires some initialization. Most of these steps are just editing the config to let git know who you are and logging in.

First we open Windows Terminal

![windows_terminal_1](https://lh3.googleusercontent.com/WOAkk6YV1fS88AORmVqgjEE7HNDbp2b7HfmcNKxZgyZ6ZX2cBsXxECs438Q6150bDn20uwoDgnZ6QODRFQwGmjRJzdT6jkSMsgaFmg8cC9LyIZ93P3k7J86a7PHVim8vAtY8_kCX4QOjEImw0CzQ-JhjjvsE0q_JI-IFo1K09PIhNyE-57ag2dmUxFMy5fHY44PP3uN0A-6zYFBZGiqub8-UU3wGCiVGgBJWg22qoxSA-jd0mfVXHoa57gOg2-prfOQ1NY0kEBZJEbH3nHoMOwl1M7LKRPBWQIdoERFGbzbHeOWgFKD5bgCMHXPKp-nhfQiN3XVCMifZBktXuBELGfAnEb1Id8ptMitiKg_GigxJrzyUtZReOM72mlEkxLbW4VnWR6MLw3OVMEtGU2cVwmjEQ3pyguJoftXoJqIpPHufP_9DuQgukNnra2GwdgM1HiCkmd7pRgjQsLO-N5DWkL7Pw-ySv8iQWqQBR-I7aX6wiM7nLQ5MBA0hMICDxR_5iIGw_KW4j5A_J3VfJR4FMU5nfIPk3n49MgpXKHBG71f-iKiPoQiqdsDKeeICzvllJvZzhjsAJVcmEsyhMdDOlIJjijT6Q-yPJIm3QQ-OK9QN0F_y-vXIJ0hTteiGXpBm1mll7zL_WiV5-ACSOIKNr6esXotgeqM_p5aD_gkGZxZzZqytQxlLquCsA07jmoA5cqtnvUg3nBifWYtUpd6QdBSrepe7iyq_FPbgXEVprFU3gW4m7nNtRiWjSy-IjKY3pOxusMxTDnYnZVv_8fdZNI4EZHKiTwyepw=w527-h298-no?authuser=0)

Then we type ```git config --global user.email "{your email id}"```. This is the same email ID you used to make the github account.

![windows_terminal_2](https://lh3.googleusercontent.com/QslwoYCJXgUXoO4PZ3xP_HGjFkEMizL6P7LEQ9FQa2zKWa1oczVqGyxULmvncub7sBXM3LEL46cb7vknMOkCVT7PIOdUxP-my430Et6cmdxi8C9Kc-zFM71aBqloz6N2bkZVzcYX9J2RhFsEzmDEYqmXn-kYrt1zTubNUSipYZu6Z82ynRV4UqfcUkOSyb7j9VHPxm5mOZ9NGtkhr54gSm0iJNCY2VxvmXj0TkYm0z82XGkSELyGeOW8YcWu9CH_P-JRBt8VJNiz7zB6NAOV6gQ8fYuTL2ibulWyBP-nFjuX8HjMRU3kKMRE-LhB1bOUgsf6BWwcmD_uJMZLUz87MVv5G4aKa9riO1DtdXU5SH3LIDvEay7aTsVyBR9ia3QF6tmNBwWOBlxh7Oge_ZKi4qTehv-jpwo87rQyamcWa-00uh1r9TY11tZ-zD378KGKHAo5zXUQswz08Vp49SlMffE1VQEP7QobYWpasADSIAVv3Hjy6FIfKwaBXbhC3W5fr_1Q-kG37vzowuONvKef5ArKLfhoq6Dmqp1CcX7FYADyriH8Z_yJ6ghbi4uUeBYs6e60B_Ybd_owlf73zJa0RydF6lCcrRQ_uxF2S95LTuOjUzNd1_obB8rO8COlLom65rgDO5nA9tWkKeRumcVPmIQYulryrrJd8770AT7gN78cKK7MT9f2Bi0CNTsE8n8slSWW-n4XOKhbuJmV1qtRPcJxrFbpD-zGFUH00GD_2fhO76yPW1h7W9HJ0DzOL4a4K4xeHAMCfQHg1IEuQ5Uyz-2AhqXq3Jk-1w=w1131-h637-no?authuser=0)

The final step is ```git config --global user.name "{your username}"```. This is the username that we made while making the github account.

![windows_terminal_3](https://lh3.googleusercontent.com/hsK9nEj2RdO7JuDNNFoYNHcGsLm-wOfWiL9M0Jb6qOuRuR2Ihx6phWrPNA86G92ZxuQ5mqyF54_d5NGmnDts4hbwBZp8PDF9L1AptW0awbohqccg8Jw8p-_Zc7URUGsnCM1f2y8mujVTKYY3tAzBtGNAt4ivrso1m3ybSmoN7SiBE8gy7OVt_kNvnuR-pxGRDslJP2fOIgMIsZdlAZFKNDw4jVvgOYi7IO6uxh4I-XbyVU-MdeNP8qU9CaQmvmLyHW336Y32JxaY99v2SC3WqfYikbk9HVyu7Iu0fv1KiH3L_9TWXm2oPTVnNwWkSwilx19tcDIiXFLvEgwh95Hd2PIeYuGkZZtkm6D_v9e0C1YNZeL0xP7q3yvFAXJjgdmSVW-ymXJ7bMCsk5FM00DmZglnpj9E-60T1Spb1FPor78PmPZOf3Cy8DiOuTtq2i2Lox-3imgkS0dWpK-ObVDpuW4RB8anB_iu6YXFrU7620AbR9sVYJW7D6GuhqktzOzOzdqoNErMuoIfA08J81BWOrHpT94SxHhJ-MMkcT6MccWZIBisCplYuDlAwxYxgsAJmNsrblXtsuLfVeeqomGU7qBZaTckqCv7F5ECR3soC510PjokIZMWKYmyeKbVLyf-eR1UM0eWAfFeKlPSeysiLv7yA7Hp4F_ZuDxblgFf63jrpd4QT9YJ4IIGptk3P5hBVkUhVVC5e5O6M3cqEbHHibnBVmeyCmAz_ETLKqgmiTLjlqGPGDVSppZBnhUHrjBRwOrszduEA9dYFqFRF4lUB75dT1VQqmJDLA=w1129-h635-no?authuser=0)

Thats it. Your git install is initialized.

## STEP 5 : MAKING A GITHUB REPO

Now we make a github repository. And then we WRITE SHIT IN IT. AND THEN WE COMMIT IT. Hell yeah. Lets go.

Go to [Github](www.github.com)

![git-repo-1](https://lh3.googleusercontent.com/Vcpb6owmarRYF_YxGwrYZB-xdt0ibT_Cx-FoI_YrJlwXL065d-BbNNnxqROgaj5IFdxgZWPnDtLCKd2NtmRfHGWYFDC9Fnsz3mamCQA46dgiZRpPd8nnzQCFaeL6hwjTz5N9KX_lqLNVVBm20-J3FaojQyaHQhhYR03281pdLaReyS5YDYTe6D0XsBIgfzl9tDvU-pliIMPYmEqMcsgK8hdF9BKS9WI6TvT15lYQqUIJbTM5CQx-OvDHVsBi9Nk9yqDS6jColiEdH85uoCXE_rLu2UmCVW6LPQwwMNoJHI4k0eepH3UVAsp6GhOuuzvTR2sEg1cTGDqfJuvILmEzjGQGnBPIujOqHGaFbukfMf5Do1zKrTM_vWqoN1N56zpcVAUk-U1qC32Sfj7jWlwYZDLbK8cN56lEbV7plcEll9FRV2PcYrW5DM1rcx9xNqtEdgTvbWSWXta316EY_17vSoxL2LZ7kXM9UDi-cp5osN_A6_htH_71sogsscDoTEu-bGkkFlI1hGRJGfXfbswpWicccCwP25P27A33QmFN3YZZo2XSwrZ6A3nTNK2ZhzzVEV_2PXwAiKKtnfLJllx7Knai9v03kp2SyahCyqM_kvC21gre1lsYnd8lkq0zVTiPcYqGvCbn95BrQ4dpqWlx65n3dzZTYbxLaSF6VHM5Wm9u0siJGtAl6p8TWUHsxqn0tTCA3-5er-FykZxtSCkuV9fJ6qtJdk6QAYXHQcWIGkXs20_5LrQ3GF0hKwORat5dWAoQJyIiP2OogJqBpdfgC2cbuzP1AzhY7A=w1898-h945-no?authuser=0)
Click on the "+" in the top right and select "create repository"

![git-repo-2](https://lh3.googleusercontent.com/CgmJtdwoCnFcOBgmexMjGfAJq-y2t1cjmqD6i13YfzXn-TrNSTnL6uQOpK3zWWjUYh-2q-4MgYgDwk85UbWofreb7JytIfMBBb-fbd95wcrGLS-nIzlyKoiH_uBnQwgBam9FyR6E28Yuvg1cs66eSnFvo8Np64_bYOUAf1xyY1fkdFOg-lKnOQCVcidvJ08baK2fpMFhjt7A6brkgu2h_7bZzByTyCZbyZgl3iR7GTwFo39O6EmFqYs_7HMyNGxdStmgG6qNLuoUAbA7HhjV2Um8gcdeCDhZpM3jiFbpH6XOmusY-n6BYLyVN_kGGivDbcsVewPiFOcph2pJcty4hCPTTYMejPyEyO-QSOX9aFa8wJ7rJvwAwlIFH5r54QP033eM3jD-uQR7iQhbMyhUwSNp_qmQfESie_UYChj_7A7IB68WUwcnNBzKK0rNVchhepjQzy3C-ZDMx81gZRrWqWjpFFR93KcjgyvbboIXgOtPWqHe_wgZ0bhDmh3tQtmRVipnkWi1g2skHYDpHXWW0B6KklQbrM_-we4K98p1EZc3kWCjsIWhlTxk4AFbcwEwtv1Q-XHcJWo5IT6DF8f4pTXWfO_haQmCq3unCA9OGj56nfzZC4v2n2N03N2UCZry6UqHjpg5DCOhRR3bhbW26FK-4cYVOa90UdX87lGdfGp7HwgA-3U9mDev_GeB0zZxR__0384qeKl198bvNU3KfecseUhqgnPlGUead55ud9S3cbC_gOJlQ2Ho_mUESnSzRLqMi3qGkKRvfbc_HeyJOwZSCRQ0uiNu_A=w1903-h953-no?authuser=0)
Then give your repository any name you want. For the sake of this tutorial I'll put down "learning-github" as the name. And then click on "create respository" at the bottom of the page.

![git-repo-3](https://lh3.googleusercontent.com/cjVaXiiefKrlK8PHBEQ-nzctjUeXik4WcryFmHbFvLC12vf65GB7ppWU1TKwCTG5IHOdmz8cIweZR4EoOuSjkyMzLxb5TjlnyAO12YQ49GbAGOl7jjrQgLu6n0qVMgQrLUQyQ4ISiZIkoWgDM5hVPrcMXNZSJdBY-GBortetMuq1G-2eDoYBmQtLIQt3yCae0IFaaTHRQEnjiNf8Cjnwlc6gwJz9c-nKnjpTOmTDsmPG855UB-dOqMAsPeIkfaaRPoOJGaezgAZvEZ9zWOVXNJv_v9EHOE4I6Nv56s7M5-ylcFEH8D7lvDJpacrHpzNutWAoEijEFRX4UT4NUmLfoOW0kvz-6jnqZjY5FZwnMbqvS8JIRYORlPBT4DPJJyRq3L9g4Zpi7Pwhi6GuuKnjqmuxbZLcnpd489493COPBvQGfw6netsOiUe62Vr27gDrwltDGI04-nIL2A3NUgEjCljwiJhuEACrMIm4pHjV79k0-gl-rAy89_pB8B42k_UnNUPHcP-VLi6-Y0o_zPvupnq-sh6uxDn-njU6MBNfnpqjCE6wuAMxHDRRaQiJs8Z874Oso1rY1ZYD0VnhEFgBMZ8O07IOCb_hxBeHwkrunsDJe_Y0rFFuqReXyLPRVw2eXt65A81pLiAqSAi9Z2z911WRc6vmCi_7DXRQ4M8_zQ_JJfYHm95CX-k6WqkxGTHlByU1jjP3E4Fqg45FH2mpBagoS9I_uSC8j4PrV_Bvm44ikGdT2RWm3TkrDN7N50T7JRp8uX3gijZbXcTwvijyUXp1N0LNohsx0g=w1898-h952-no?authuser=0)
You'll be dropped on this page. This is your repository. YAY! Looks kinda empty thought. Next we'll clone this add a file and push the changes.
First you need to copy the section that has a URL below "Quick Setup"

![git-repo-4](https://lh3.googleusercontent.com/GhQAMpyXVTWVtDih6oOsrig0pcH_URPcCQSiqsnZHGylbLz8aaKAl6F9sh3O-CP8GEvqOGpYKd6u13k5yhYRVPM_yE68aH0aL7Nle9Qjr8Wbaj-ECFXos3QCVHt_bUC7LOyWpNbzNw1rm2DmYYsmXX0MA2l7-F8b1zDjFrlYEe0mH1g6T8zDbVz5nw2SgFIVRwFxQM3LifPnHiQ9j0IdmOCL7pfmoa9XSuKIt8GNGIBpp1Yb5_k2A2WPazQb25TDAEKRO2zTB1lI3vy7l2FsnRSevH8NFzhHOyDF0-qOv3sktZxTOW9FatrnjB3rcIFoPz0mEwdfGUC4RW0nvQog7Av_tlvwDVEcYV61EhcJRvmUl_zY-Qi1Q0nkD9NNX5OOavFVzY9lZ6iWNM_YVZozufCTxFlWtqrbzcwjjVcuOMMX5qHAPcwRaXxBaPd5Ra3rcFQ23X6zO4nTzruI1QtVWGdKi0x17VZGSc7tlZNKKQmxbmjI3Lru7zv_h3cPdb_9TKPQgHxa3AQ4OnlbaYe3EatdoKSeZN56MAMGV4gr-7AUVAj-qMRZz7unh_ZhC4vFIh1V9j1tV7Es4snOVllrBJmUdy1MdfVUYH5iYoyXHn5ggsQmcxRGQFLE_eJm5MYC-zHysnmR-WbGC3RyyFSdl5o21lJDXvyKwKM0pa2o6kk6cDWT1x9yqlmwdMcRhuktQynIB9x0ACXVSUMMCKlL-BDbW0EpaDpasSjyQDwzJPg-7G4nv3Kww_mwkdoGPZkZHAjPJY7XQRkTU5Tme3wG8x08UjPMdkBoEg=w1147-h646-no?authuser=0)
Go to your D drive or anywhere where you want the repository to live on your computer. Right-click and select "Open in Windows Terminal".

![git-repo-5](https://lh3.googleusercontent.com/Zlze_UtRis38e3ier8iJXyEqRjnHKXFM9YSc_TyBQEWn5v2poKUbD_CD60pFUhF6KsGZo2SxHWAR1e5WhNDMJVudSkdz4ltskwJR7OC-vsluVDluUvvxttzu5ueZmhMebr0Pg-DFzIB7wCFctBD9EWsf1swGRYgkHF5Ojydk53-jnBP28bLpCNY8hOLJxuN_jEHA43GbbkWWWXAkugDhwjDVkCKcxP_CmlD_o5FSSYn7Ipwjbrh5dcOgWi7VD0ls_Olx1-7mTl6UEc5jnvgnUwIrGrWeMAFXhXc_059phJg64U5mXxCDBKzSgoHcN_s94yN61fyecen9BQ5AdytimqR9klOE9CQ9hwq4xt57ZlE8eeJIYbmpUFVb0__4WJfMcPP6eJQM9A7wl72EkPszKwtLJHI740-gAe85e_lVy1mMyT92wtCFJAIHzrnje8eKq1DpTTkE5CjPFikXc3Qd7uY8mUZPBDfS4r_D_exRVnRRHpWJv6pVsKxmUcokcnGNenQcUrKxFjLXVhEZtAuvwM4dn9KO91iBBKIjMZs3REndrXpGuVnILxfS40xC7ix1_zX7_-lPJ_yqeta--4ZQUV3mczGlrNt51be8W1_KJhKEu6WExxbSpSqJ-CBxcNIwDBLypvBVDVPIX43uE3bI_860fFLRsQyPh1VUKyMwtd4M8mjbN8CX-W52OckQadgapNExX0MSPfA7ZOOxMQCTRvaoloTc_TkeVP0RBI7TByEfC8Cmjc2t-pQGXnwAqNG31hKwKF-I5qaXu7nAU0wDqEUh_xf6W9MeEQ=w1134-h637-no?authuser=0)
Next we clone the repository using ```git clone {paste the URL you copied}```
voila! Now if you look in the File explorer we can see a folder names "learning-github". Thats out github repository

![git-repo-6](https://lh3.googleusercontent.com/9Xp8RMBxzaB_f7psNsWRkrcI3Y0a0cgfYDOAQvEp7kt8cFe6VJqyWQiZg8EufAEv_OgxGXzYn0fNNmqLqGxCNO1lOcRrCZLvAx4bPD4Spk_SWkpV8mRwLa130H-TyIG4yQ_TuSoJuwiifoq42oM4jdR_-KLny7_pQ_yES52pp2sEMOtI8CYgcxojQYqq_E-My9P8xmsETPbywomzv3k-_eLa5CrN4Et3o4l_v993ANrw4wiBDod-dTltMMVWnM26JyYDrs45rjXwmTirqKT8kNAEJs26gvHOCn9MCnWpZCn2NVJIklA6OTsQ6ShaMRI4jhZQIn8WlAqMA10CTMrgcrqHmk-SaWVBMAF4aX5QF-YT6lZICDHr8mMLgbsec-SdDCEYgmSDvnGNZ2yWPVyZ1nKZDwaPO5KmUCQl3-KtyxBFor6JmBrgr8abanDS8DkfltxLL2Klmjfy3PgFQlZU2M0RqCsOwENZohxVh6olEyfY6wMOcDMQGoWjgES0SZ6fV7lEwbaOnIxjArhDldxSxReu_ZuytFTBhfZQUwZfbs7d_GpVSIsdejTXU5SQCJvcTZy-skwkIedIs-bOa5V6PX2nXysQGxQ_2yzsA7fi4vrVUZSgebEAHA1XzIML82e0i-EgwKAku2ErxNkYsN87nHacNAaIkyEQnSCjOi7cp4P4LZztBoQ71-HHi-uI4AgVYET1MAKUgKMMsK2IdqdxS1My1KJb5qhAguOe3oD0htqx1K6FdsBA_TcX6IPt6xsvLhUDiA87yzjG0DMByXFsTWVJTv3SgRyycA=w1142-h629-no?authuser=0)

Now we open the folder. Right-click and add a text document. Name it anything. Doesn't matter. This is just to show you how to push a commit.

![git-repo-7](https://lh3.googleusercontent.com/GTRBy0S-6OrOhdCQbtPZ1cc0byJx4tT57PRctqTKrL1OK0kZU6kT6Z7HZFLN70To7V4h0xguyy8X6tqDHw8ezNFofi63lunob27umgsaUoPAskW8ktvk1pig-mzJvQHfaPxlcVDGBUQRwenPa2S__x_sUlgVRewhvHTkwvW2txXJG7ICgebQQ49u4MygYUzKX1RXisr58mb6Vi32SWbZq7FRkrSabc2QC5jFQSPBNjvuLxEgOOBKAgB84ltrfOy2gDx7UlFCwVm-xx3wp825udh16edfYgjURPSxX4DJIUhinVPThRymiiFNtSgYKBjXEbRBVmZFEpoSteMHiiW5ADqi29rfak7MGem_xV5qAt_bKd8cyw_E844h6PALlQjSmHh9fznblSSQjexR3PiqExsVSxcY6ddGl7h8fTuMmCIGt9py5QpI_3yQBQtktSxaP_Y2JgCw73-ARJYBNJi_YjQqZpLxRqGYjbGyp69Qo325iMeV7O8tCl54O6RDTFa4zAEj1QBbQkNg01SPrcWrarOE0I3o4gNT5EDl1Tpqru6_liFpuS7JiHMUCacr8nPzqqN0I11mfkilKp3mgqUB77COMwiqTUyshM86n_auQ0FQ11EQyWPZhisEsoDlndOMPywg4p6ZbmLxrzqiIBf1GeYSD_SoRvUWCLufxZ9axr7l-RVwqnbjDLqjxz2-42XwNfpN7HuUwR9zPWacMgPQoJWy3cze4VzWIZmdvbWZ3d415S9HJBaxcE3GOBPErlaXweSL4G_vFVXnO4SJFt-Xn8ybjNazCdTcfQ=w1144-h633-no?authuser=0)
I've named the file letsgo.txt.
After this right-click anywhere in the empty space in the folder and "Open in windows terminal"

![git-repo-8](https://lh3.googleusercontent.com/rTtp2YcRqdnp1KorOheYF8IgJCYjX6xlIaxOkluJfuRpidWi37sG1vwEIoOfUFf8vDwooYcA1v6GOtZrjNnMEd97kKGGOBmwwUHpU12cK4C_KG1tZ7nMJGS6O-l_gh5ae0sDnEmbFClSGOuDD0e5hlBLlfrI7h0erE48PM6h7p010KZFh-uy5sCfpD6zT320j99RQ4ROd2dvABjHMEuZMGoabPVUhvNtEvwUFbO-eszF30Ft6L_vEST5DZN2TyZ19fe1TVHimTLswMcNM0DNoSVSL72pK8qzmiiADdyjB8XgI8gRuVW9VkNSH6eTM87GdxSKpyZWqg4gaU_UCigqNAIGN080BKBb52vMwDmZt750Zd-BSWorpxOnGyVbRjppDlWy6HxPfk9yMV9-vf1VeVCS26Is1P-mrGHARye74dBT28-vlTBAhpOrjZGuYnAW6C98OgBy_f7GjILd65K_bdKDGnwi2n_7iMCHV5XChLBTbMf9NeS6s9WpELtmWh0QdYKDCvyuPKvuNWHlBKh5omEjBFoJOHFrWrkZUIoJWxMsrWtGW7ExpfUMxZC4R8UymlYyxJFbI08KUgGzLRuTnCzzZKjEBq26eKPlgF_iopJ1OSDjOBE5P7z67rvsQUsOYFG8dmBi4EvMnxEG8fZFIXpWZqbcNQWBVF9rlTLW_Jo6kh2uPuO52lACLrX6q1DKY1t6v4enZ6wWNccTnPi9uXwPpY-4HIzRcVpkIeCI5LXXgnokoS09QqXYxOLe7vMSNWJ8klmrowPsHJI2sj-3cDh5-JdRf0SITg=w1133-h640-no?authuser=0)
First we do ```git add .``` Git keeps track of all the changes youve made in that folder. When you do ```git add .``` It adds all the changed and new files to the commit. It basically gets the file ready to commit and push.

![git-repo-9](https://lh3.googleusercontent.com/oqRS7aCoHUEpK5MMf6bxqAmDT5fkFtlqTtGYbgSMhy64cnPy3iTcuDSq3iuJUW740OwLRr9NfaVU6zWScRvq5vQRPrta3n6ekDaYaBr5LfuiODx5kNMyx8JnXk6AD7nQ2vORZPnInW-jvZbGNjMLjwX_-JtHANrBYJUHY9hdcXaLy2tA0woFYmLUR5sL3oO_t9-OgNGuYrvHE-BW_v9y7ESXwFvPD3h0ueOMcvdri-XjhMJGi0OXlxFduDJKkQRNKP_rkLeGZcKQk3KcN7iYKtwk3FB2ODYHNloChPTBR63HIbo0wC_mYH_oH3-YBKgnsv9Ajc9JNYlmZ12RwHT7eBo88QQQTCP9C-WiOy4pUuNfXp-bXGRCFRE3YQkQh9cje-swha2i5IBjxrXcb-iidEIx3UbJJUScmhfBQv_GJWvBr53IgxhkU_K71PRRiG3oCjX9HPu3NHlQIl_cT5FqBlnYJ9SQhZS7AH7hccy880emyTmaefioqLkst7S9SxDhleDFaySEDzQn0goTMFkBZS3y0hlRxkg-KbxNCWCz4HJ0hkbpBLBQy_TCZZRPSfW4x7IjiSCsIMbdKOT33unDcGjotIpYacmFL6XD33QgzHLD9qGgWTY6g9VCZMt4WI3Aln7x06k4Vhym_x2WdJTEDTPEzyMr66bt4HHUKxp44U1-ZmX9EKWN31HFQMBAuKUGjSqtT7NtE273b8g9SseUJwISWRdt9XbfL_QJUDUxMaW1NdO95JK5C69FboMKOyhPg1fAHb71BPtTA0PYJOkGLDcsgxO5oyiA_g=w1132-h641-no?authuser=0)
Then we do ```git commit -m "Initial commit"```
This command commits all the changes. and makes it ready to push. You can put anything in the inverted commas. That is basically your commit changelog.

![git-repo-10](https://lh3.googleusercontent.com/gfQXKsw8sPFSIucjelod8PcFuKCvWBSQhyvE3GHrQ_bxjY1TBa4fCYMhqto7v5PAljKRa3Fbt4THmbxdiN6SF67vIeaCDMZhIsmKTzehwE0aXM9XE_rhnIIlEWoHO4-GMe7hFU1mjqZBkHOVYHAJg_OioUj6vlA-Ggcn2MEMNKSJbX5QAP4H8bg6C2uieKDZqiFkMICuP0Xa785svBvzLntae90fgl7XFnZxChFKCKJpfK6ehf3JxRcuaMhG_JeVIgEP04mUvKyEUp2J4s2dr1ovZKsNNzia3_vbA4fyRRcAiF-8zDR5mDL-jaRy7f_uoIl_XwvCfhNLaPJeXQyGCiLGTWMHWhh3LYCOc0lV9WfVccDJdatbUjBgWeYSDFgCPFOnascMnbkcD954CASOBBzC6SffvrySXy6QRl8dGS_7dCgVCnIbi7vjMzMr5e9PPjGJxvrtyXyMVEZncav5fkZLtxRs2Nqhx-VeGn6WeVkPY8AT-6qM5RRqXF0nV0CN48yegzB-rtmCFLO6pb51GW9HaHKLguNx-5tmSCcBDLm4tFUaAdYvXibjHHbz-KXnFp9NikQ1EpNCPBCdhq6sAx_5a0ud1B8i4qhYMuWB9lzNZ1I6FyM8CKutyD6fcr0cRl-h5wN3jOe4aI7uiWYc3VEtwJLAmC_ZtfI1WKpI30ghpXVVaWv7OGFpfQfSgHdh3VweChc2GIYy40gj6DzugU9JZdHw2z1YIYAXCzdk43M-J0cyMNCy2Bf24Jt37QOaqiSmDf4pWPfRdQDro0AO57Je72MXeTet9g=w1133-h638-no?authuser=0)
Finally we do ```git push``` this will push all the changes to your repository.
(The first time you do this you will be prompted to login. Login using your browser and give git to manage your github).

You can now go to your github account. Open the repository and see that the letsgo.txt that we made is now present on the webpage.

![git-repo-11](https://lh3.googleusercontent.com/uRy6SMx_jBVYB00PQIjTxRpKXmbd_eLktd3gDuh074J3APHCcah4-56fsRnRl-_hUakdByA3vnFKKtEV_CcTm6DTumxsNwBBHGpmF5odrEHdNb7ZlcLt0gLyUKAri-JEnKjZj8scrzXyCaCVrijvX522OCX4dUfQwdAtRCepiYOg4c-nquixu7BopzuVi87_R0IpcPheXGQP5dtvA8VHOm7aQ2JfkpbkbMdd7t4B-_mFA9JzPno1HqrJGUOcBb0yVMubl1H-GqWJ6XbAVeVFdhy-lsvPldLOLtassbuKXNoPjomj243frcizID0OCSJvqTUnZ1yNsRC8hk-72Yfxl7BpHW-bf7O8x-qYPiDTJlSbY-6bNYTWD0Q0HHnhXeKh92sDQMvBLxb_HKn4X78hfc8FoROuaXP_ssuIqprD8Zr4G-7B2HgzOHOX4_RwpcP78kB0LgWXqf8Hu8UoBBiWVpmKAcN1DXK4ShAC4bPME-gP963Mv_86NdFV7tp-85PKkhcZl0wudyYvNu6OxuV7j_JCimBc2AB1bGK4X58QZuzrZ2Xip_dLZwaVEA5PpTgNqjEJbYx7rCtO4t2BjPqrc0Uqv2MjRj_AO4BWBIQ_RdM2J3FvD3OzCGv7g145QqlIn1poUQ8BBZ4-p8pEdsiYOsgxvlHYMt6dacn0Er9RKeBbf3vixQYJleh8C2zSxXj_uFwMW308hzaX6unzV1RsYRY6hmRQ-Tc0qGxidPoiX87HwFpOgCR4FocODIsGTCXSCJjfr326LapdWHoOVZa4Nsteb3R2zYcIVQ=w1920-h950-no?authuser=0)


## YOURE DONE!!!!

Yeah thats it. You have successfully installed git, created a repository, cloned that repository, added a file to it and pushed changes to the repository. You are all set to now use git and github.

I've been saying git and github for the whole guide beacuse there are alternatives to github. There is [GitLab](https://about.gitlab.com/), [BitBucket](https://bitbucket.org/product), [SourceForge](https://sourceforge.net/), etc. These all use git as their version control system. You can even host your own instance or website and use Git to push to that. 

Hope this was helpful to newcomers. I will be updating this if I learn something new or I remember that I forgot to add something.

## SOME GOOD PRACTICES

1. Always pull before starting work and before adding something to the commit tree. Especially if there are multiple people working on the repo or if you are working on it from multiple computers. Doing a ```git pull``` before doing anything else never hurts.
2. Write detailed commit messages so that you know exactly which commit broke your software. I used to commit with "lmao", "commit please", "yes commit". Trust me, It will take a few seconds to write a detailed commit out but will help you out a lot in the long run.
3. Have fun. The graphs are an addiction.

## MORE READING:
1. [https://www.atlassian.com/git/glossary](https://www.atlassian.com/git/glossary)
2. [https://git-scm.com/docs/gittutorial](https://git-scm.com/docs/gittutorial)

