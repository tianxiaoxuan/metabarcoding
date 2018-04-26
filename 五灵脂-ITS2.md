## 五灵脂ITS2数据处理
*数据拆分前，各文库分别进行处理
###### fastqc
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI1-MIX_clean_R1.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI1-MIX_clean_R2.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI2_clean_R1.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI2_clean_R2.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI3_clean_R1.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI3_clean_R2.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI4_clean_R1.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI4_clean_R2.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI5_clean_R1.fq.gz -o ./
    fastqc /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI5_clean_R2.fq.gz -o ./
######质量过滤
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI1-MIX_clean_R1.fq.gz /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI1-MIX_clean_R2.fq.gz ZWI1_R1_paired.fq ZWI1_R1_unpaired.fq ZWI1_R2_paired.fq ZWI1_R2_unpaired.fq -threads 10 SLIDINGWINDOW:10:25 MINLEN:100
    # Input Read Pairs: 1811589 Both Surviving: 1279527 (70.63%) Forward Only Surviving: 341009 (18.82%) Reverse Only Surviving: 29102 (1.61%) Dropped: 161951 (8.94%)
    #ZWI1_R1_paired.fq-2198047，ZWI1_R2_paired.fq-2434077
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI2_clean_R1.fq.gz /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI2_clean_R2.fq.gz ZWI2_R1_paired.fq ZWI2_R1_unpaired.fq ZWI2_R2_paired.fq ZWI2_R2_unpaired.fq -threads 10 SLIDINGWINDOW:10:25 MINLEN:100
    #Input Read Pairs: 1446034 Both Surviving: 1112463 (76.93%) Forward Only Surviving: 210576 (14.56%) Reverse Only Surviving: 33024 (2.28%) Dropped: 89971 (6.22%)
    #ZWI2_R1_paired.fq-1989248，ZWI2_R2_paired.fq-2093031
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI3_clean_R1.fq.gz /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI3_clean_R2.fq.gz ZWI3_R1_paired.fq ZWI3_R1_unpaired.fq ZWI3_R2_paired.fq ZWI3_R2_unpaired.fq -threads 10 SLIDINGWINDOW:10:25 MINLEN:100
    # Input Read Pairs: 1184719 Both Surviving: 922845 (77.90%) Forward Only Surviving: 152480 (12.87%) Reverse Only Surviving: 31447 (2.65%) Dropped: 77947 (6.58%)
    #ZWI3_R1_paired.fq-1664039，ZWI3_R2_paired.fq-1731663
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI4_clean_R1.fq.gz /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI4_clean_R2.fq.gz ZWI4_R1_paired.fq ZWI4_R1_unpaired.fq ZWI4_R2_paired.fq ZWI4_R2_unpaired.fq -threads 10 SLIDINGWINDOW:10:25 MINLEN:100
    # Input Read Pairs: 1095345 Both Surviving: 839421 (76.64%) Forward Only Surviving: 155622 (14.21%) Reverse Only Surviving: 28518 (2.60%) Dropped: 71784 (6.55%)
    #ZWI4_R1_paired.fq-1495537，ZWI4_R2_paired.fq-1574915
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI5_clean_R1.fq.gz /mnt/meta/meta-五灵脂/测序结果/Its2/clean_data/ZWI5_clean_R2.fq.gz ZWI5_R1_paired.fq ZWI5_R1_unpaired.fq ZWI5_R2_paired.fq ZWI5_R2_unpaired.fq -threads 10 SLIDINGWINDOW:10:25 MINLEN:100
    #Input Read Pairs: 967741 Both Surviving: 765977 (79.15%) Forward Only Surviving: 127459 (13.17%) Reverse Only Surviving: 18256 (1.89%) Dropped: 56049 (5.79%)
    #ZWI5_R1_paired.fq-1360197，ZWI5_R2_paired.fq-1430024
###### 双端拼接(QIIME)
    join_paired_ends.py -f ZWI1_R1_paired.fq -r ZWI1_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #fastqjoin.join.fastq序列数982355（76.7%，较其他库比例高）
    join_paired_ends.py -f ZWI2_R1_paired.fq -r ZWI2_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #fastqjoin.join.fastq序列数398258
    join_paired_ends.py -f ZWI3_R1_paired.fq -r ZWI3_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #fastqjoin.join.fastq序列数347644 
    join_paired_ends.py -f ZWI4_R1_paired.fq -r ZWI4_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #fastqjoin.join.fastq序列数350805
    join_paired_ends.py -f ZWI5_R1_paired.fq -r ZWI5_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #fastqjoin.join.fastq序列数315479
###### 数据拆分
    #OBITOOLS
    #文库1
    ngsfilter -t ZWI1-13.txt -u failure13.fastq fastqjoin.join.fastq > ZWI1-13.fastq
    ngsfilter -t ZWI1-14.txt -u failure14.fastq fastqjoin.join.fastq > ZWI1-14.fastq
    ngsfilter -t ZWI1-15.txt -u failure15.fastq fastqjoin.join.fastq > ZWI1-15.fastq
    cat ZWI1-13.fastq ZWI1-14.fastq ZWI1-15.fastq > ZWI1.assigned.fastq
    #去掉forward/reverse_tag=None,余380979条序列，约84.8%(仅拆分)
    #文库2
    ngsfilter -t ZWI2-13.txt -u failure13.fastq fastqjoin.join.fastq > ZWI2-13.fastq
    ngsfilter -t ZWI2-14.txt -u failure14.fastq fastqjoin.join.fastq > ZWI2-14.fastq
    ngsfilter -t ZWI2-15.txt -u failure15.fastq fastqjoin.join.fastq > ZWI2-15.fastq
    cat ZWI2-13.fastq ZWI2-14.fastq ZWI2-15.fastq > ZWI2.assigned.fastq
    #去掉forward/reverse_tag=None,余155783条序列，约39%
    #文库3
    ngsfilter -t ZWI3-13.txt -u failure13.fastq fastqjoin.join.fastq > ZWI3-13.fastq
    ngsfilter -t ZWI3-14.txt -u failure14.fastq fastqjoin.join.fastq > ZWI3-14.fastq
    ngsfilter -t ZWI3-15.txt -u failure15.fastq fastqjoin.join.fastq > ZWI3-15.fastq
    cat ZWI3-13.fastq ZWI3-14.fastq ZWI3-15.fastq > ZWI3.assigned.fastq
    #去掉forward/reverse_tag=None,余144667条序列，约41.6%
    #文库4
    ngsfilter -t ZWI4-13.txt -u failure13.fastq fastqjoin.join.fastq > ZWI4-13.fastq
    ngsfilter -t ZWI4-14.txt -u failure14.fastq fastqjoin.join.fastq > ZWI4-14.fastq
    ngsfilter -t ZWI4-15.txt -u failure15.fastq fastqjoin.join.fastq > ZWI4-15.fastq
    cat ZWI4-13.fastq ZWI4-14.fastq ZWI4-15.fastq > ZWI4.assigned.fastq
    #去掉forward/reverse_tag=None,余156604条序列，约44.6%
    #文库5
    ngsfilter -t ZWI5-13.txt -u failure13.fastq fastqjoin.join.fastq > ZWI5-13.fastq
    ngsfilter -t ZWI5-14.txt -u failure14.fastq fastqjoin.join.fastq > ZWI5-14.fastq
    ngsfilter -t ZWI5-15.txt -u failure15.fastq fastqjoin.join.fastq > ZWI5-15.fastq
    cat ZWI5-13.fastq ZWI5-14.fastq ZWI5-15.fastq > ZWI5.assigned.fastq
    #去掉forward/reverse_tag=None,余119317条序列，约37.8%
###### 合并数据
    cat ZWI1/ZWI1.assigned.fastq ZWI2/ZWI2.assigned.fastq ZWI3/ZWI3.assigned.fastq ZWI4/ZWI4.assigned.fastq ZWI5/ZWI5.assigned.fastq > temp/ZWI.assigned.fastq
    obiconvert --fasta-output temp/ZWI.assigned.fastq > temp/ZWI.assigned.fasta #fastq to fasta
    obiannotate -k sample -k forward_tag -k reverse_tag temp/ZWI.assigned.fasta > temp/ZWI.assigned2.fasta
###### 去除单端assigned
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs temp/ZWI.assigned2.fasta -label_word forward_tag=None -fastaout temp/fnone.fa -notmatched temp/ZWI.trim-fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs temp/ZWI.trim-fn.fasta -label_word reverse_tag=None -fastaout temp/rnone.fa -notmatched temp/ZWI.trim-fn-rn.fasta
###### 格式转换
    #只保留sample信息
    obiannotate -k sample temp/ZWI.trim-fn-rn.fasta > temp/ZWI.trim.fasta
    #改为usearch接受的格式
    awk 'BEGIN{FS=OFS=";"}NF=1' temp/ZWI.trim.fasta > temp/ZWI.trim1.fasta#去掉第一个分号后的内容
    sed 's/ sample/;sample/g' temp/ZWI.trim1.fasta > temp/ZWI.trim2.fasta#空格变分号
    #观察文件中是否有多余的信息未被去除
    #核酸序列转化为大写
    /home/tianxiaoxuan/tools/seqkit seq -u temp/ZWI.trim2.fasta > temp/ZWI.trim3.fasta
###### 合并核酸到一行,这是下一步按length过滤数据的必要步骤。431729条序列
    fasta_formatter -i temp/ZWI.trim3.fasta -o temp/ZWI.trim4.fasta
###### trim侧缘序列
    perl ITSx -t T --preserve T --cpu 16 -i ZWI.trim4.fasta -o ZWI
    3月7日 20:55~22:10，trim结果文件ZWI.ITS2.fasta，剩余430755条序列
###### 去除phix污染(usearch)
    #去除phix污染 hits，100.0% Filtering for phix, 0 hits (0.0%)
    /home/tianxiaoxuan/tools/usearch10 -filter_phix temp/ZWI.ITS2.fasta -output temp/ZWI_phix.fasta -alnout temp/phix_hits.txt
    #检查usearch可否读取，以及样品总数，成功，135个样品(共192个样品，不加空管共174个样品)
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/ZWI_phix.fasta -output temp/ZWI_phix_samples.txt
###### 去冗余(usearch)
    #去冗余，按总数据量的百万分之一设置最小丰度reads数. 430755 seqs, 80004 uniques, 62618 singletons (78.3%)，3642 uniques written, 79764 clusters size < 8 discarded (99.7%)
    /home/tianxiaoxuan/tools/usearch10 -fastx_uniques temp/ZWI_phix.fasta -fastaout temp/ZWI_unique.fasta -minuniquesize 8 -sizeout 
    #此时113个sample可找到！
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/ZWI_unique.fasta -output temp/ZWI_unique_samples.txt 
    #10603
    grep '>' -c temp/ZWI_unique.fasta
###### 使用unoise3去噪
    /home/tianxiaoxuan/tools/usearch10 -unoise3 temp/ZWI_unique.fasta -zotus temp/zotus.fa -minsize 8
    # 100.0% 720 good, 47 chimeras
###### 使用AWK命令格式化OTU ID
    awk 'BEGIN {n=1}; />/ {print ">OTU_" n; n++} !/>/ {print}' temp/zotus.fa > result/zrep_seqs.fa
###### 按长度排序
    /home/tianxiaoxuan/tools/usearch10 -sortbylength result/zrep_seqs.fa -fastaout result/rep_seqs_sort.fa -minseqlength 10
	fasta_formatter -i result/rep_seqs_sort.fa -o result/rep_seqs.fa
###### 95% OTU聚类
    /home/tianxiaoxuan/tools/usearch10 -cluster_smallmem result/rep_seqs.fa -id 0.95 -centroids temp/otus95.fa
	#100.0% 284 clusters, max size 29, avg 2.5
    cp temp/otus95.fa result/rep_seqs1.fa
    #生成otu表，422712 / 430755 mapped to OTUs (98.1%)
    /home/tianxiaoxuan/tools/usearch10 -usearch_global temp/ZWI_phix.fasta -db result/rep_seqs1.fa -otutabout temp/otu_table.txt -biomout temp/otu_table.biom -strand both -id 0.95 -threads 10
###### BIOM表（OTU表）探查
    #必需经此转化
    biom convert -i temp/otu_table.txt -o temp/otu_table.biom --table-type="OTU table" --to-json
    #查看biom表 135个样品，283个OTU
    biom summarize-table -i temp/otu_table.biom 
    #拷贝biom表到result目录
    cp temp/otu_table.biom result/otu_table.biom
###### 进入qiime镜像
    docker start qiime
    docker attach qiime
###### 过滤低丰度的OTU
    #按OTU丰度过滤：选择相对丰度均值大于万分之一的OTU
    filter_otus_from_otu_table.py --min_count_fraction 0.0001 -i result/otu_table.biom -o result/otu_table2.biom
    #查看过滤后结果：135个样品，213个OTU
    biom summarize-table -i result/otu_table2.biom 
###### 转换OTU表并筛选最终序列
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table2.biom -o result/otu_table2.txt --table-type="OTU table" --to-tsv
    #筛选最终OTU表中对应的OTU序列
    filter_fasta.py -f result/rep_seqs.fa -b result/otu_table2.biom -o result/rep_seqs2.fa 	
###### blast比对分类信息
    nohup blastn -query result/rep_seqs2.fa -db /home/share/blastdb/nt/nt -outfmt 5 -evalue 10 -max_target_seqs 5 -gapopen 5 -gapextend 2 -num_threads 16 > result/rep_seqs2.xml 2>&1 &
###### megan整理分类信息
* 95%——属，90%——科及以上
* 200个OTU得到分类信息，1个OTU not hit，3个OTU not assigned，
* 导出分类信息并核对，根据分类信息，对OTU进行剔除：otu340/3/403/83
* result/otu_table3.txt
######抽平
    biom convert -i result/otu_table3.txt -o result/otu_table3.biom --table-type="OTU table" --to-json
    biom summarize-table -i result/otu_table3.biom
    #剩余135个样品，204个OTU
    #按count>=800过滤样品
    filter_samples_from_otu_table.py -i result/otu_table3.biom -o result/otu_table4.biom -n 800
    #查看过滤后结果：72个样品，204个OTU
    biom summarize-table -i result/otu_table4.biom
    #按最小数据量抽平
    single_rarefaction.py -i result/otu_table4.biom -o result/otu_table_rare.biom -d 800
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table_rare.biom -o result/otu_table_rare.txt --table-type="OTU table" --to-tsv
######表格整理
* otu 502，517，567，157,475,546,349
* otu 449,717,201,225
* otu 203,379
* otu443,590
* otu 153,432
* otu 547,18，63
* otu 289,374
* otu 25,251
* otu 593,435,43
* otu 326,458
* otu 397,515
