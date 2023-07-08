# song backup db
mmd motion and camara back up database.  
someof songs has lyrics file (`.lrc`).

# images
This `images` folder stores the cover image of MP3 files.  
(It's useless except for the list view. And it's updated asynchronically.)

# upload guide (ko)
업로드 할 곡 예시:
`ロキ - ナナヲアカリ.mp3`,
`ロキ.mp3`  
파일명을 이렇게 해야되는 이유<sup id="a1">[[1]](#f1)</sup>  
앨범이라 다른곡이 있다면?<sup id="a2">[[엘범가이드]](#qa)</sup>
왜 `inst`(MR) 이 없나?<sup id="a2">[[엘범가이드]](#qa)</sup>
1. 폴더를 생성.
`/audios/ロキ` 라는 경로가 되도록
2. 그 후 [info.json](./info.json) 을 편집.

```json
{
    "f": "ロキ",
    "m": [
        "ロキ/ロキ.mp3",
        "ロキ/ロキ - ナナヲアカリ.mp3"
    ],
    "artist": "MIKU",
    "another": [
        "NANAOAKARI"
    ],
    "tags": [
        "MIKU",
        "VOCALOID",
        "NANAOAKARI"
    ],
    "preview" : 0,
    "raw": true,
    "r": 3
}
```
#### 필수
- `f` : 일본어 혹은 영어로 곡명 혹은 앨범명을 작성.
- `m` : 하위 파일구조
- `"raw": true` : 압축파일 인지 아닌지 표기
- `"r": 3` : 저장소 번호
- `tags` : 파일 검색, 분류에 쓰이는 태그들.
- `artist` : 메인파일의 아티스트, 여러명일 경우에는 쉼표 ( , ) 로 분리.

#### 비 필수
- `another` : 추가파일의 아티스트
- `maker` : 보컬트레이너, 레이블(엘범) 아티스트
- `atrys` : 커버파일 검색 시도 리스트
- `preview` : 미리듣기 재생시작 시각은 [ms] 로 기록바람 (1초 = 1000ms)

# Q&A
1. Q: 앨범명이 `A Vol.1` 혹은 `A Disk.1` 이라면?
   혹은 `A Disk.2` 가 있다면?  
   A: `audios/A` 가 없다면 만들어서 해당 폴더에 하위 컨텐츠를 같이 둔다.  
   (`Disk`,`Vol` 같은 이름은 파일 조회시 오류를 발생.)

2. Q: `아티스트`는 같은데 앨범은 여러게?  
   A: `audios/아티스트` 폴더를 만들어서 여러 앨범의 컨텐츠를 같이 둔다.
    
3. Q: 왜 `inst`(MR), `.flac`가 없나?  
   A: DB 저장용량이 한정 되어 있기에 목소리가 들어있는 `.mp3` 만 있어야 됩니다.  
   ( `inst`(MR)은 [bgm](./bgms/) 폴더에 올려주셨으면... )

# license
This db is made for educational and research purpose.
### Note: maybe somefiles will delete with the original author's objection.

# footnote’s (각주)
<b id="f1">1</b> : 이름이 겹칠때 쓰는걸 권장하며, 가급적 "-" 로 분리표시 하는건 하지 말아주세요.  
