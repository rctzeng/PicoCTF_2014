# PNG or Not?
用hex editor 打開
 * 察看png format 的標記：[wiki page](https://en.wikipedia.org/wiki/Portable_Network_Graphics)
```
Critical chunks
A decoder must be able to interpret critical chunks to read and render a PNG file.

IHDR must be the first chunk; it contains (in this order) the image's width, height, bit depth and color type.[10]
PLTE contains the palette; list of colors.
IDAT contains the image, which may be split among multiple IDAT chunks. Such splitting increases filesize slightly, but makes it possible to generate a PNG in a streaming manner. The IDAT chunk contains the actual image data, which is the output stream of the compression algorithm.
IEND marks the image end.
```
 * [image.png](image.png)在 IEND 之後似乎還有東西：
```
AE 42 60 82 37 7A BC AF 27 1C 00 03 B8 64 D3 C1 1A 00 00 00 00 00 00 00 50 00 00 00 00 00 00 00 B5 6B 69 46 00 22 92 C6 AE 77 46 B4 23 6D F7 5D C0 C0 A4 DC 1F A8 38 05 57 B9 76 3E 20 00 01 04 06 00 01 09 1A 00 07 0B 01 00 01 23 03 01 01 05 5D 00 00 01 00 0C 14 00 08 0A 01 DC E1 0D DE 00 00 05 01 11 13 00 66 00 6C 00 61 00 67 00 2E 00 74 00 78 00 74 00 00 00 14 0A 01 00 90 D6 20 07 48 DB CF 01 15 06 01 00 20 00 00 00 00 00    
```
 * ```AE 42 60 82 37 7A``` 是 .7z檔的magic number
 * 把這串東西存成[flag.7z](flag.7z)，再用7z 解壓縮得到含有```EKSi7MktjOpvwesurw0v```的flag.txt
