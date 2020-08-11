# hello-world
the first program
Hi I come from CHAIN,want to learn something.
%% 读取与语音信号信息
[s,fs]=audioread('G:\曹盘盘\项目开发\20200618-配电柜声音信号.wav');
info=audioinfo('G:\曹盘盘\项目开发\20200618-配电柜声音信号.wav') %得到声音的格式、位数、频率等

%% 绘制时域原始语音信号图并做FFT分析
%绘制时域原始语音信号
figure(1);
subplot(211);
plot(s);%输入信号时域曲线
title('原始信号时域');
xlabel('时间');
ylabel('振幅');
%绘制FFT分析图形
N=200000;
y=fft(s,N);
magy=abs(y);
f=(0:length(y)-1)*fs/length(y);
subplot(212);
plot(f(1:N/2),magy(1:N/2));
xlabel('频率（Hz）');
ylabel('幅值');
title('N=200000(b)');
axis([0 3000 0 50]);
grid on %打开网格
