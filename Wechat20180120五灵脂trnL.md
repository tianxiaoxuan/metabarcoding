## 五灵脂trnL数据处理20180119


* 数据位置 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/
* raw data，接头序列按trimmomatic提供的接头文件做修改

######Trim接头+质量过滤
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT1_H3JHCDMXX_L1_1.fq.gz /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT1_H3JHCDMXX_L1_2.fq.gz ZWT1_R1_paired.fq ZWT1_R1_unpaired.fq ZWT1_R2_paired.fq ZWT1_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 5500375 Both Surviving: 5088729 (92.52%) Forward Only Surviving: 136418 (2.48%) Reverse Only Surviving: 197723 (3.59%) Dropped: 77505 (1.41%)
    #5088729
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT2_H3NTLDMXX_L1_1.fq.gz /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT2_H3NTLDMXX_L1_2.fq.gz ZWT2_R1_paired.fq ZWT2_R1_unpaired.fq ZWT2_R2_paired.fq ZWT2_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 7242354 Both Surviving: 6902492 (95.31%) Forward Only Surviving: 118695 (1.64%) Reverse Only Surviving: 43701 (0.60%) Dropped: 177466 (2.45%)
    # 6902492
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT3 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT3 ZWT3_R1_paired.fq ZWT3_R1_unpaired.fq ZWT3_R2_paired.fq ZWT3_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 2351838 Both Surviving: 1974769 (83.97%) Forward Only Surviving: 106552 (4.53%) Reverse Only Surviving: 63328 (2.69%) Dropped: 207189 (8.81%)
    #1974769
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/补测/raw_data/ZWT3 /mnt/meta/meta-五灵脂/测序结果/trnL/补测/raw_data/ZWT3 ZWT3b_R1_paired.fq ZWT3b_R1_unpaired.fq ZWT3b_R2_paired.fq ZWT3b_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 1493849 Both Surviving: 1189436 (79.62%) Forward Only Surviving: 74914 (5.01%) Reverse Only Surviving: 47304 (3.17%) Dropped: 182195 (12.20%)
    #1189436
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT4_H3NTLDMXX_L1_1.fq.gz /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT4_H3NTLDMXX_L1_2.fq.gz ZWT4_R1_paired.fq ZWT4_R1_unpaired.fq ZWT4_R2_paired.fq ZWT4_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 8093944 Both Surviving: 7542582 (93.19%) Forward Only Surviving: 165081 (2.04%) Reverse Only Surviving: 54858 (0.68%) Dropped: 331423 (4.09%)
    # 7542582
    java -jar /home/tianxiaoxuan/tools/Trimmomatic-0.36/trimmomatic-0.36.jar PE -phred33 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT5 /mnt/meta/meta-五灵脂/测序结果/trnL/raw_data/ZWT5 ZWT5_R1_paired.fq ZWT5_R1_unpaired.fq ZWT5_R2_paired.fq ZWT5_R2_unpaired.fq -threads 10 ILLUMINACLIP:/home/sunliran/metabarcoding/Faeces_Trogopterori/trnL/20180120/TruSeq2-PE.fa:2:30:10:1:true SLIDINGWINDOW:10:25 MINLEN:60
    #Input Read Pairs: 7074548 Both Surviving: 6729725 (95.13%) Forward Only Surviving: 155105 (2.19%) Reverse Only Surviving: 47374 (0.67%) Dropped: 142344 (2.01%)
    #6729725
######fastqc
    fastqc ZWT1_R1_paired.fq
    fastqc ZWT1_R2_paired.fq
    fastqc ZWT2_R1_paired.fq
    fastqc ZWT2_R2_paired.fq
    fastqc ZWT3_R1_paired.fq
    fastqc ZWT3_R2_paired.fq
    fastqc ZWT3b_R1_paired.fq
    fastqc ZWT3b_R2_paired.fq
    fastqc ZWT4_R1_paired.fq
    fastqc ZWT4_R2_paired.fq
    fastqc ZWT5_R1_paired.fq
    fastqc ZWT5_R2_paired.fq
######双端拼接
    #usearch
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT1_R1_paired.fq -reverse ZWT1_R2_paired.fq -fastqout ZWT1.fq
    #4725372  Merged (4.7M, 92.86%)
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT2_R1_paired.fq -reverse ZWT2_R2_paired.fq -fastqout ZWT2.fq
    #6492856  Merged (6.5M, 94.07%)
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT3_R1_paired.fq -reverse ZWT3_R2_paired.fq -fastqout ZWT3.fq
    #1607120  Merged (1.6M, 81.38%)
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT3b_R1_paired.fq -reverse ZWT3b_R2_paired.fq -fastqout ZWT3b.fq
    #1137116  Merged (1.1M, 95.60%)
    # WK3/ZWT3.fq与WK3b/ZWT3b.fq合并，ZWT3/ZWT3all.fq
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT4_R1_paired.fq -reverse ZWT4_R2_paired.fq -fastqout ZWT4.fq
    #6892576  Merged (6.9M, 91.38%)
    /home/tianxiaoxuan/tools/usearch10 -fastq_mergepairs ZWT5_R1_paired.fq -reverse ZWT5_R2_paired.fq -fastqout ZWT5.fq
    #6347675  Merged (6.3M, 94.32%)
###### 数据拆分
    #文库1
    ngsfilter -t ZWT1-10.txt -u failure10.fastq ZWT1.fq > ZWT1-10.fastq
    ngsfilter -t ZWT1-11.txt -u failure11.fastq ZWT1.fq > ZWT1-11.fastq
    ngsfilter -t ZWT1-12.txt -u failure12.fastq ZWT1.fq > ZWT1-12.fastq
    ngsfilter -t ZWT1-13.txt -u failure13.fastq ZWT1.fq > ZWT1-13.fastq
    ngsfilter -t ZWT1-15.txt -u failure15.fastq ZWT1.fq > ZWT1-15.fastq
    cat ZWT1-10.fastq ZWT1-11.fastq ZWT1-12.fastq ZWT1-13.fastq ZWT1-15.fastq > ZWT1.assigned.fastq#序列数2487148,其中forward_tag=None 378416，reverse_tag=None 760837
    #文库2
    ngsfilter -t ZWT2-10.txt -u failure10.fastq ZWT2.fq > ZWT2-10.fastq
    ngsfilter -t ZWT2-11.txt -u failure11.fastq ZWT2.fq > ZWT2-11.fastq
    ngsfilter -t ZWT2-12.txt -u failure12.fastq ZWT2.fq > ZWT2-12.fastq
    ngsfilter -t ZWT2-13.txt -u failure13.fastq ZWT2.fq > ZWT2-13.fastq
    ngsfilter -t ZWT2-15.txt -u failure15.fastq ZWT2.fq > ZWT2-15.fastq
    cat ZWT2-10.fastq ZWT2-11.fastq ZWT2-12.fastq ZWT2-13.fastq ZWT2-15.fastq > ZWT2.assigned.fastq #序列数4236352,其中forward_tag=None 974822，reverse_tag=None 1412424
    #文库3
    ngsfilter -t ZWT3-10.txt -u failure10.fastq ZWT3all.fq > ZWT3-10.fastq
    ngsfilter -t ZWT3-11.txt -u failure11.fastq ZWT3all.fq > ZWT3-11.fastq
    ngsfilter -t ZWT3-12.txt -u failure12.fastq ZWT3all.fq > ZWT3-12.fastq
    ngsfilter -t ZWT3-13.txt -u failure13.fastq ZWT3all.fq > ZWT3-13.fastq
    ngsfilter -t ZWT3-15.txt -u failure15.fastq ZWT3all.fq > ZWT3-15.fastq
    cat ZWT3-10.fastq ZWT3-11.fastq ZWT3-12.fastq ZWT3-13.fastq ZWT3-15.fastq > ZWT3.assigned.fastq #序列数1405358,其中forward_tag=None 384342，reverse_tag=None 519857
    #文库4
    ngsfilter -t ZWT4-10.txt -u failure10.fastq ZWT4.fq > ZWT4-10.fastq
    ngsfilter -t ZWT4-11.txt -u failure11.fastq ZWT4.fq > ZWT4-11.fastq
    ngsfilter -t ZWT4-12.txt -u failure12.fastq ZWT4.fq > ZWT4-12.fastq
    ngsfilter -t ZWT4-13.txt -u failure13.fastq ZWT4.fq > ZWT4-13.fastq
    ngsfilter -t ZWT4-15.txt -u failure15.fastq ZWT4.fq > ZWT4-15.fastq
    cat ZWT4-10.fastq ZWT4-11.fastq ZWT4-12.fastq ZWT4-13.fastq ZWT4-15.fastq > ZWT4.assigned.fastq#4217504条序列，其中forward_tag=None 956567，reverse_tag=None 1329068
    #文库5
    ngsfilter -t ZWT5-10.txt -u failure10.fastq ZWT5.fq > ZWT5-10.fastq
    ngsfilter -t ZWT5-11.txt -u failure11.fastq ZWT5.fq > ZWT5-11.fastq
    ngsfilter -t ZWT5-12.txt -u failure12.fastq ZWT5.fq > ZWT5-12.fastq
    ngsfilter -t ZWT5-13.txt -u failure13.fastq ZWT5.fq > ZWT5-13.fastq
    ngsfilter -t ZWT5-15.txt -u failure15.fastq ZWT5.fq > ZWT5-15.fastq
    cat ZWT5-10.fastq ZWT5-11.fastq ZWT5-12.fastq ZWT5-13.fastq ZWT5-15.fastq > ZWT5.assigned.fastq #序列数4126846,其中forward_tag=None 878265，reverse_tag=None 1241937
###### 合并数据
    cat ZWT1/ZWT1.assigned.fastq ZWT2/ZWT2.assigned.fastq ZWT3/ZWT3.assigned.fastq ZWT4/ZWT4.assigned.fastq ZWT5/ZWT5.assigned.fastq > temp/ZWT.assigned.fastq
    obiconvert --fasta-output temp/ZWT.assigned.fastq > temp/ZWT.assigned.fasta #fastq to fasta
    obiannotate -k sample -k forward_tag -k reverse_tag temp/ZWT.assigned.fasta > temp/ZWT.assigned2.fasta
###### 去除单端assigned
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs temp/ZWT.assigned2.fasta -label_word forward_tag=None -fastaout temp/fnone.fa -notmatched temp/ZWT.trim-fn.fasta
    /home/tianxiaoxuan/tools/usearch10 -fastx_getseqs temp/ZWT.trim-fn.fasta -label_word reverse_tag=None -fastaout temp/rnone.fa -notmatched temp/ZWT.trim-fn-rn.fasta
###### 格式转换
    #只保留sample信息
    obiannotate -k sample temp/ZWT.trim-fn-rn.fasta > temp/ZWT.trim.fasta
    #改为usearch接受的格式
    sed 's/ sample/;sample/g' temp/ZWT.trim.fasta > temp/ZWT.trim2.fasta
    #观察文件中是否有多余的信息未被去除
    #核酸序列转化为大写
    /home/tianxiaoxuan/tools/seqkit seq -u temp/ZWT.trim2.fasta > temp/ZWT.trim3.fasta
###### 合并核酸到一行,这是下一步按length过滤数据的必要步骤。7636500条序列
    fasta_formatter -i temp/ZWT.trim3.fasta -o temp/ZWT.trim4.fasta
###### 长度筛选
    #保留长度10-143bp的序列。剩余7549107条序列
    /home/tianxiaoxuan/tools/akutils-v1.2/scripts/filter_fasta_by_length.sh temp/ZWT.trim4.fasta 10 143 > temp/ZWT.trim4.10-143.fasta #输出文件的名称必须是这样的格式
    grep -c '>' temp/ZWT.trim4.10-143.fasta
###### 去除phix污染(usearch)
    #去除phix污染 hits，100.0% Filtering for phix, 0 hits (0.0%)
    /home/tianxiaoxuan/tools/usearch10 -filter_phix temp/ZWT.trim4.10-143.fasta -output temp/ZWT_phix.fasta -alnout temp/phix_hits.txt
    #检查usearch可否读取，以及样品总数，成功，185个样品(共198个样品，不加空管共180个样品)
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/ZWT_phix.fasta -output temp/ZWT_phix_samples.txt
###### 去冗余(usearch)
    #去冗余，按总数据量的百万分之一设置最小丰度reads数. 7549107 seqs, 82888 uniques, 50176 singletons (60.5%)
    /home/tianxiaoxuan/tools/usearch10 -fastx_uniques temp/ZWT_phix.fasta -fastaout temp/ZWT_unique.fasta -minuniquesize 8 -sizeout 
    #此时163个sample可找到！
    /home/tianxiaoxuan/tools/usearch10 -fastx_get_sample_names temp/ZWT_unique.fasta -output temp/ZWT_unique_samples.txt 
    #10603
    grep '>' -c temp/ZWT_unique.fasta
###### 使用unoise3去噪
    /home/tianxiaoxuan/tools/usearch10 -unoise3 temp/ZWT_unique.fasta -zotus temp/zotus.fa -minsize 8
    # 100.0% 610 good, 59 chimeras 
###### 使用AWK命令格式化OTU ID
    awk 'BEGIN {n=1}; />/ {print ">OTU_" n; n++} !/>/ {print}' temp/zotus.fa > result/zrep_seqs.fa
###### 按长度排序
    /home/tianxiaoxuan/tools/usearch10 -sortbylength result/zrep_seqs.fa -fastaout result/rep_seqs_sort.fa -minseqlength 10
	fasta_formatter -i result/rep_seqs_sort.fa -o result/rep_seqs.fa
###### 98% OTU聚类
    /home/tianxiaoxuan/tools/usearch10 -cluster_smallmem result/rep_seqs.fa -id 0.98 -centroids temp/otus98.fa
	#100.0% 578 clusters, max size 4, avg 1.1
    cp temp/otus98.fa result/rep_seqs1.fa
    #生成otu表，6602171 / 7549107 mapped to OTUs (87.5%)
    /home/tianxiaoxuan/tools/usearch10 -usearch_global temp/ZWT_phix.fasta -db result/rep_seqs1.fa -otutabout temp/otu_table.txt -biomout temp/otu_table.biom -strand both -id 0.98 -threads 10
###### BIOM表（OTU表）探查
    #必需经此转化
    biom convert -i temp/otu_table.txt -o temp/otu_table.biom --table-type="OTU table" --to-json
    #查看biom表 184个样品，458个OTU
    biom summarize-table -i temp/otu_table.biom 
    #拷贝biom表到result目录
    cp temp/otu_table.biom result/otu_table.biom
###### 挂载qiime
    docker start qiime
    docker attach qiime
###### 过滤低丰度的OTU
    #按OTU丰度过滤：选择相对丰度均值大于万分之一的OTU
    filter_otus_from_otu_table.py --min_count_fraction 0.0001 -i result/otu_table.biom -o result/otu_table2.biom
    #查看过滤后结果：184个样品，177个OTU
    biom summarize-table -i result/otu_table2.biom 
###### 转换OTU表并筛选最终序列
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table2.biom -o result/otu_table2.txt --table-type="OTU table" --to-tsv
    #筛选最终OTU表中对应的OTU序列
    filter_fasta.py -f result/rep_seqs.fa -b result/otu_table2.biom -o result/rep_seqs2.fa 	
###### blast比对分类信息
    nohup blastn -query result/rep_seqs2.fa -db /home/share/blastdb/nt/nt -outfmt 5 -evalue 10 -max_target_seqs 5 -gapopen 5 -gapextend 2 -num_threads 16 > result/rep_seqs2.xml 2>&1 &
###### megan整理分类信息
* 98%——属，90%——科及以上
* 133个OTU得到分类信息，44个OTU not hit，其中三个OTU为细菌（69、167、174）,其余OTU均为Streptophyta门物种
* 导出分类信息并核对，根据分类信息，对OTU进行剔除：细菌OTU及not hit的序列（not hit序列需确定产生原因，网页blast看）
* result/otu_table3.txt
######抽平
    biom convert -i result/otu_table3.txt -o result/otu_table3.biom --table-type="OTU table" --to-json
    biom summarize-table -i result/otu_table3.biom
    #剩余184个样品，130个OTU
    #按count>=3000过滤样品
    filter_samples_from_otu_table.py -i result/otu_table3.biom -o result/otu_table4.biom -n 3000
    #查看过滤后结果：156个样品，130个OTU
    biom summarize-table -i result/otu_table4.biom
    #按最小数据量抽平
    single_rarefaction.py -i result/otu_table4.biom -o result/otu_table_rare.biom -d 3000
    #转换biom格式OTU表为文本OTU表格
    biom convert -i result/otu_table_rare.biom -o result/otu_table_rare.txt --table-type="OTU table" --to-tsv
######表格信息整合
* 核对分类信息，只鉴定到科及科以上的，属一级分类信息写not assigned，并以OTU编号区分。
* 到科以下但未到属的，保留最后一级分类信息，标注otu编号
* 属级分类信息相同的OTU进行合并，otu表进行同样的合并
* 合并情况如下
  * otu144、57、67、100合并为otu57，Streptophyta;asterids;Dipsacales;Adoxaceae;Viburnum
  * otu11、20、47合并为otu11，Streptophyta;asterids;Ericales;Ericaceae;Rhododendron
  * otu143、77、58合并为otu58，Streptophyta;Liliopsida;Asparagales;Amaryllidaceae;Allium
  * 余123个otu
  * 去掉空管样品：K1-C,K3-R,K5-R,余153个样品。