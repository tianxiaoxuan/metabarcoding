###### fastqc
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC1_H33LGCCXY_L8_1.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC1_H33LGCCXY_L8_2.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC2_H33LGCCXY_L8_1.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC2_H33LGCCXY_L8_2.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC3_H33YTCCXY_L1_1.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC3_H33YTCCXY_L1_2.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC4_H33YTCCXY_L1_1.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC4_H33YTCCXY_L1_2.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC5_H33YTCCXY_L1_1.clean.fq.gz -o ./
    fastqc /mnt/wlz/测序结果/Cytb/clean_data/ZWC5_H33YTCCXY_L1_2.clean.fq.gz -o ./
######质量过滤
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/wlz/测序结果/Cytb/clean_data/ZWC1_H33LGCCXY_L8_1.clean.fq.gz /mnt/wlz/测序结果/Cytb/clean_data/ZWC1_H33LGCCXY_L8_2.clean.fq.gz ZWC1_R1_paired.fq ZWC1_R1_unpaired.fq ZWC1_R2_paired.fq ZWC1_R2_unpaired.fq -threads 10 -trimlog logfile SLIDINGWINDOW:10:25 MINLEN:100
    # Input Read Pairs: 5092353 Both Surviving: 4701382 (92.32%) Forward Only Surviving: 196754 (3.86%) Reverse Only Surviving: 109775 (2.16%) Dropped: 84442 (1.66%)
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/wlz/测序结果/Cytb/clean_data/ZWC2_H33LGCCXY_L8_1.clean.fq.gz /mnt/wlz/测序结果/Cytb/clean_data/ZWC2_H33LGCCXY_L8_2.clean.fq.gz ZWC2_R1_paired.fq ZWC2_R1_unpaired.fq ZWC2_R2_paired.fq ZWC2_R2_unpaired.fq -threads 10 -trimlog logfile SLIDINGWINDOW:10:25 MINLEN:100
    # 20580069
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/wlz/测序结果/Cytb/clean_data/ZWC3_H33YTCCXY_L1_1.clean.fq.gz /mnt/wlz/测序结果/Cytb/clean_data/ZWC3_H33YTCCXY_L1_2.clean.fq.gz ZWC3_R1_paired.fq ZWC3_R1_unpaired.fq ZWC3_R2_paired.fq ZWC3_R2_unpaired.fq -threads 10 -trimlog logfile SLIDINGWINDOW:10:25 MINLEN:100
    #Input Read Pairs: 15957648 Both Surviving: 14179024 (88.85%) Forward Only Surviving: 1248488 (7.82%) Reverse Only Surviving: 121187 (0.76%) Dropped: 408949 (2.56%)
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/wlz/测序结果/Cytb/clean_data/ZWC4_H33YTCCXY_L1_1.clean.fq.gz /mnt/wlz/测序结果/Cytb/clean_data/ZWC4_H33YTCCXY_L1_2.clean.fq.gz ZWC4_R1_paired.fq ZWC4_R1_unpaired.fq ZWC4_R2_paired.fq ZWC4_R2_unpaired.fq -threads 10 -trimlog logfile SLIDINGWINDOW:10:25 MINLEN:100
    #Input Read Pairs: 19269532 Both Surviving: 18123314 (94.05%) Forward Only Surviving: 450712 (2.34%) Reverse Only Surviving: 352692 (1.83%) Dropped: 342814 (1.78%)
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/wlz/测序结果/Cytb/clean_data/ZWC5_H33YTCCXY_L1_1.clean.fq.gz /mnt/wlz/测序结果/Cytb/clean_data/ZWC5_H33YTCCXY_L1_2.clean.fq.gz ZWC5_R1_paired.fq ZWC5_R1_unpaired.fq ZWC5_R2_paired.fq ZWC5_R2_unpaired.fq -threads 10 -trimlog logfile SLIDINGWINDOW:10:25 MINLEN:100
    #Input Read Pairs: 19377651 Both Surviving: 18646328 (96.23%) Forward Only Surviving: 303233 (1.56%) Reverse Only Surviving: 240248 (1.24%) Dropped: 187842 (0.97%)
###### 双端拼接(QIIME)
    join_paired_ends.py -f ZWC1_R1_paired.fq -r ZWC1_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    # 17395682
    join_paired_ends.py -f ZWC2_R1_paired.fq -r ZWC2_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    # 20536085
    join_paired_ends.py -f ZWC3_R1_paired.fq -r ZWC3_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #14087094
    join_paired_ends.py -f ZWC4_R1_paired.fq -r ZWC4_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #18007487
    join_paired_ends.py -f ZWC5_R1_paired.fq -r ZWC5_R2_paired.fq -m fastq-join -j 10 -p 20 -o ./
    #18543423
###### 数据拆分
    #OBITOOLS
    #文库1
    ngsfilter -t ZWC1-10.txt -u failure10.fastq fastqjoin.join.fastq > ZWC1-10.fastq
    ngsfilter -t ZWC1-11.txt -u failure11.fastq fastqjoin.join.fastq > ZWC1-11.fastq
    ngsfilter -t ZWC1-12.txt -u failure12.fastq fastqjoin.join.fastq > ZWC1-12.fastq
    cat ZWC1-10.fastq ZWC1-11.fastq ZWC1-12.fastq > ZWC1.assigned.fastq
    #文库2
    ngsfilter -t ZWC2-10.txt -u failure10.fastq fastqjoin.join.fastq > ZWC2-10.fastq
    ngsfilter -t ZWC2-11.txt -u failure11.fastq fastqjoin.join.fastq > ZWC2-11.fastq
    ngsfilter -t ZWC2-12.txt -u failure12.fastq fastqjoin.join.fastq > ZWC2-12.fastq
    cat ZWC2-10.fastq ZWC2-11.fastq ZWC2-12.fastq > ZWC2.assigned.fastq
    #文库3
    ngsfilter -t ZWC3-10.txt -u failure10.fastq fastqjoin.join.fastq > ZWC3-10.fastq
    ngsfilter -t ZWC3-11.txt -u failure11.fastq fastqjoin.join.fastq > ZWC3-11.fastq
    ngsfilter -t ZWC3-12.txt -u failure12.fastq fastqjoin.join.fastq > ZWC3-12.fastq
    cat ZWC3-10.fastq ZWC3-11.fastq ZWC3-12.fastq > ZWC3.assigned.fastq
    #文库4
    ngsfilter -t ZWC4-10.txt -u failure10.fastq fastqjoin.join.fastq > ZWC4-10.fastq
    ngsfilter -t ZWC4-11.txt -u failure11.fastq fastqjoin.join.fastq > ZWC4-11.fastq
    ngsfilter -t ZWC4-12.txt -u failure12.fastq fastqjoin.join.fastq > ZWC4-12.fastq
    cat ZWC4-10.fastq ZWC4-11.fastq ZWC4-12.fastq > ZWC4.assigned.fastq
    #文库5
    ngsfilter -t ZWC5-10.txt -u failure10.fastq fastqjoin.join.fastq > ZWC5-10.fastq
    ngsfilter -t ZWC5-11.txt -u failure11.fastq fastqjoin.join.fastq > ZWC5-11.fastq
    ngsfilter -t ZWC5-12.txt -u failure12.fastq fastqjoin.join.fastq > ZWC5-12.fastq
    cat ZWC5-10.fastq ZWC5-11.fastq ZWC5-12.fastq > ZWC5.assigned.fastq
###### 数据合并
    cat zwc1/ZWC1.assigned.fastq zwc2/ZWC2.assigned.fastq zwc3/ZWC3.assigned.fastq zwc4/ZWC4.assigned.fastq zwc5/ZWC5.assigned.fastq > temp/ZWC1-5.assigned.fastq
###### 格式转换，去除多余注释（操作目录为各输入文件的目录）
    #fastq to fasta
    obiconvert --fasta-output ZWC1bc.assigned.fastq > ZWC1bc.assigned.fasta 
    obiconvert --fasta-output ZWC2bc.assigned.fastq > ZWC2bc.assigned.fasta 
    obiconvert --fasta-output ZWC3bc.assigned.fastq > ZWC3bc.assigned.fasta 
    obiconvert --fasta-output ZWC4bc.assigned.fastq > ZWC4bc.assigned.fasta 
    obiconvert --fasta-output ZWC5bc.assigned.fastq > ZWC5bc.assigned.fasta 
    obiconvert --fasta-output ZWC6.assigned.fastq > ZWC6.assigned.fasta 
    obiconvert --fasta-output ZWC1-5.assigned.fastq > ZWC1-5.assigned.fasta 
    #去除多余注释
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC1bc.assigned.fasta > ZWC1bc.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC2bc.assigned.fasta > ZWC2bc.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC3bc.assigned.fasta > ZWC3bc.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC4bc.assigned.fasta > ZWC4bc.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC5bc.assigned.fasta > ZWC5bc.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC6.assigned.fasta > ZWC6.assigned1.fasta
    obiannotate -k sample -k forward_tag -k reverse_tag ZWC1-5.assigned.fasta > ZWC1-5.assigned1.fasta
###### 去除单端barcode比对到样品的序列(usearch)
    #去除forward_tag=None的序列
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC1bc.assigned1.fasta -label_word forward_tag=None -notmatched ZWC1bc_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC2bc.assigned1.fasta -label_word forward_tag=None -notmatched ZWC2bc_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC3bc.assigned1.fasta -label_word forward_tag=None -notmatched ZWC3bc_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC4bc.assigned1.fasta -label_word forward_tag=None -notmatched ZWC4bc_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC5bc.assigned1.fasta -label_word forward_tag=None -notmatched ZWC5bc_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC6.assigned1.fasta -label_word forward_tag=None -notmatched ZWC6_trim_fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC1-5.assigned1.fasta -label_word forward_tag=None -notmatched ZWC1-5_trim_fn.fasta
    #查看是否成功,查看序列数，剩余5606335条序列
    grep -c 'forward_tag=None' temp/ZWC_trim_fn.fasta
    grep -c '>' temp/ZWC_trim_fn.fasta
    #去除reverse_tag=None的序列
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC1bc_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC1bc_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC2bc_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC2bc_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC3bc_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC3bc_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC4bc_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC4bc_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC5bc_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC5bc_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC6_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC6_trim_fn_rn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs ZWC1-5_trim_fn.fasta -label_word reverse_tag=None -notmatched ZWC1-5_trim_fn_rn.fasta
######只保留sample信息
    obiannotate -k sample ZWC1bc_trim_fn_rn.fasta > ZWC1bc.assigned2.fasta
    obiannotate -k sample ZWC2bc_trim_fn_rn.fasta > ZWC2bc.assigned2.fasta
    obiannotate -k sample ZWC3bc_trim_fn_rn.fasta > ZWC3bc.assigned2.fasta
    obiannotate -k sample ZWC4bc_trim_fn_rn.fasta > ZWC4bc.assigned2.fasta
    obiannotate -k sample ZWC5bc_trim_fn_rn.fasta > ZWC5bc.assigned2.fasta
    obiannotate -k sample ZWC6_trim_fn_rn.fasta > ZWC6.assigned2.fasta
    obiannotate -k sample ZWC1-5_trim_fn_rn.fasta > ZWC1-5.assigned2.fasta
######合并序列
    cat temp/ZWC1-5.assigned2.fasta ../Cytb补测/zwc1/ZWC1bc.assigned2.fasta ../Cytb补测/zwc2/ZWC2bc.assigned2.fasta ../Cytb补测/zwc3/ZWC3bc.assigned2.fasta ../Cytb补测/zwc4/ZWC4bc.assigned2.fasta ../Cytb补测/zwc5/ZWC5bc.assigned2.fasta ../Cytb中成药/cwc1/ZWC6.assigned2.fasta > temp/ZWC.assigned.fasta
######查看序列数，剩余19613716条序列
    grep -c 'reverse_tag=None' temp/ZWC.assigned.fasta
    grep -c 'forward_tag=None' temp/ZWC.assigned.fasta
    grep -c '>' temp/ZWC.assigned.fasta
    #更改为useach认可的格式
    awk 'BEGIN{FS=OFS=";"}NF=1' temp/ZWC.assigned.fasta > temp/ZWC.assigned1.fasta
    sed 's/ sample/;sample/g' temp/ZWC.assigned1.fasta > temp/ZWC.assigned2.fasta
    #序列转换为大写
    /home/tianxiaoxuan/tools/seqkit seq -u temp/ZWC.assigned2.fasta> temp/ZWC.assigned3.fasta
    #合并核酸到一行,这是下一步按length过滤数据的必要步骤。
    fasta_formatter -i temp/ZWC.assigned3.fasta -o temp/ZWC.line.fasta
###### 只保留长度等于102的序列
    #只保留长度等于102的序列。输出为ZWC.line.102-102.fasta,剩余17523656条序列
    /home/tianxiaoxuan/tools/akutils-v1.2/scripts/filter_fasta_by_length.sh temp/ZWC.line.fasta 102 102 > temp/ZWC.line.102-102.fasta
    grep -c '>' temp/ZWC.line.102-102.fasta
    tail -n 35047294 temp/ZWC.line.102-102.fasta > temp/ZWC.tail.fasta
    head -n 20 temp/ZWC.line.102-102.fasta > 102head.fasta #删去有问题的插入
    cat temp/ZWC.tail.fasta 102head.fasta > temp/ZWC.line.102-102.correct.fasta
###### 去除phix污染(usearch)
    #去除phix污染 0 hits，可略
    /home/tianxiaoxuan/tools/usearch10 -filter_phix temp/ZWC.line.102-102.fasta -output temp/ZWC_phix.fasta -alnout temp/phix_hits.txt
    #检查usearch可否读取，以及样品总数，成功，176个样品
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/ZWC_phix.fasta -output temp/ZWC_phix_samples.txt
###### 合并长度筛选后的中药和中成药数据
    cat temp/ZWC.line.102-102.correct.fasta ../Cytb中成药/temp/CWC.line.102-102.fasta > temp/cytb.all.fasta
###### 去冗余(usearch)
    #去冗余，按总数据量的百万分之一设置最小丰度reads数. 14641 uniques written
    vsearch --derep_fulllength temp/cytb.all.fasta -output temp/cytb_unique.fasta --minuniquesize 8 --sizeout 
    #此时150个sample可找到！
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/cytb_unique.fasta -output cytb_unique_samples.txt 
    #14641
    grep -c '>' temp/cytb__unique.fasta

###### 使用unoise3去噪
    /home/tianxiaoxuan/tools/usearch10 -unoise3 temp/cytb_unique.fasta -zotus temp/zotus.fa -minsize 8
    #100.0% 372 good, 733 chimeras 
###### 使用AWK命令格式化OTU ID
    awk 'BEGIN {n=1}; />/ {print ">OTU_" n; n++} !/>/ {print}' temp/zotus.fa > result/zrep_seqs.fa
###### 93% OTU聚类
    /home/tianxiaoxuan/tools/usearch10 -cluster_smallmem result/zrep_seqs.fa -id 0.93 -centroids temp/otus93.fa
    cp temp/otus93.fa result/rep_seqs.fa
    #生成otu表，20846083 / 20893708 mapped to OTUs (99.8%)
    /home/tianxiaoxuan/tools/usearch10 -usearch_global temp/cytb.all.fasta -db result/rep_seqs.fa -otutabout temp/otu_table.txt -strand both -id 0.93 -threads 10
###### BIOM表（OTU表）探查
    #必需经此转化
    biom convert -i temp/otu_table.txt -o temp/otu_table.biom --table-type="OTU table" --to-json
    #查看biom表 224个样品，94个OTU,共249个样品
    biom summarize-table -i temp/otu_table.biom 
    #拷贝biom表到result目录
    cp temp/otu_table.biom result/otu_table.biom
######运行qiime
###### 过滤低丰度的OTU
    #按OTU丰度过滤：选择相对丰度均值大于万分之一的OTU
    filter_otus_from_otu_table.py --min_count_fraction 0.0001 -i result/otu_table.biom -o result/otu_table2.biom
    #查看过滤后结果：只有223个样品，25个OTU
    biom summarize-table -i result/otu_table2.biom 
###### 转换OTU表并筛选最终序列
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table2.biom -o result/otu_table2.txt --table-type="OTU table" --to-tsv
    #筛选最终OTU表中对应的OTU序列
    filter_fasta.py -f result/rep_seqs.fa -b result/otu_table2.biom -o result/rep_seqs2.fa 
###### 检查可否编码蛋白，进一步排除错误OTU。目前看拖拽至geneious中目检最为便捷。注意选择正确密码子表
    #发现4个错误otu（3个终止子突变或插入缺失：otu6、12、236以及12个细菌污染：otu32）。是在OTU步删除或是在unique步做编码检测？前者彻底删除序列，后者原始序列可能map到其他OTU。先按前者进行，彻底。如何根据OTU名 删除otu表 尚需研究。
    #按序列名（错误otu）删除OTU表，之后为221 samples 21个OTU
    filter_otus_from_otu_table.py -e temp/rep_seqs2_extraction.fasta -i result/otu_table2.biom -o result/otu_table3.biom
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table3.biom -o result/otu_table3.txt --table-type="OTU table" --to-tsv
    #筛选最终OTU表中对应的OTU序列
    filter_fasta.py -f result/rep_seqs.fa -b result/otu_table3.biom -o result/rep_seqs3.fa
 
###### blast比对分类信息
    nohup blastn -query result/rep_seqs3.fa -db /home/share/blastdb/nt/nt -outfmt 5 -evalue 10 -max_target_seqs 5 -gapopen 5 -gapextend 2 -num_threads 16 > result/rep_seqs3.xml 2>&1 &
###### MEGAN
* result/rep_seqs3.xml和result/rep_seqs3.fa导入megan，identity设置93-species，86-genus，80-family及以上
* otu40 青霉素，删
* otu31、otu8飞鼠，嵌合，删
* otu2、otu108复齿鼯鼠
* otu39 人，删
* otu34 鱼，删
* otu202 无分类，删
* otu346 花栗鼠，不是在中国有分布的种，删
* otu175 比对到三个分类，前后相似性不一致，删
* otu1、2、33、53、108、139合并复齿鼯鼠
对rep_seqs3.fa进行上述剔除，生成rep_seqs4.fa
######重新生成OTU表
    /home/tianxiaoxuan/tools/usearch10 -usearch_global temp/cytb.all.fasta -db result/rep_seqs4.fa -otutabout temp/otu_table4.txt -strand both -id 0.93 -threads 10
    #19094137 / 20893708 mapped to OTUs (91.4%)
    biom convert -i temp/otu_table4.txt -o result/otu_table4.biom --table-type="OTU table" --to-json
    biom summarize-table -i result/otu_table4.biom
    #剩余220个样品，中药样品169，中成药样品45，13个OTU


######标准化(在本实验中不需要)
    biom convert -i result/otu_table4.txt -o result/otu_table4.biom --table-type="OTU table" --to-json
    biom summarize-table -i result/otu_table4.biom
    #剩余224个样品，7个OTU
    #按count>=500过滤样品
    filter_samples_from_otu_table.py -i result/otu_table4.biom -o result/otu_table5.biom -n 500
    #查看过滤后结果：只有166个样品，7个OTU
    biom summarize-table -i result/otu_table5.biom
    #按最小数据量抽平
    single_rarefaction.py -i result/otu_table5.biom -o result/otu_table_rare.biom -d 500
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table_rare.biom -o result/otu_table_rare.txt --table-type="OTU table" --to-tsv
    #按中药和中成药拆分成两个表，中药131个样品，中成药35个样品
