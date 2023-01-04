import cv2
from google.colab.patches import cv2_imshow

vid =cv2.VideoCapture('./TRAIN_001.mp4')               # 비디오 캡쳐 객체 생성

if vid.isOpened():                                     # 비디오 캡쳐 객체가 정상적으로 open되어있는지 확ㅇ닌
    fps = vid.get(cv2.CAP_PROP_FPS)                    
    f_count = vid.get(cv2.CAP_PROP_FRAME_COUNT)        
    f_width = vid.get(cv2.CAP_PROP_FRAME_WIDTH)        
    f_height = vid.get(cv2.CAP_PROP_FRAME_HEIGHT)
    
    print("Frames per second : ", fps, 'FPS')          # 초당 프레임 개수
    print("Frame count : ",f_count)                    # 프레임 개수
    print("Frame width : ",f_width)                    # 프레임 가로길이
    print("Frame height : ", f_height)                 # 프레임 세로길이
    
    
while vid.isOpened():                                  # 비디오 캡쳐 객체가 정상적으로 open되어있는지 확인 
    ret, frame = vid.read()                            # 비디오의 한 프레임씩 읽기
    if ret:
        re_frame = cv2.resize(frame, (round(f_width*2),round(f_height*2)))
        cv2_imshow(re_frame)
        key = cv2.waitKey(10)                          # 특정 시간동안 키보드 입력 대기 
        
        if key == ord('q'):
            break
    else:
        break
        
vid.release()                                          # 오픈한 캡쳐 객체 해제 
cv2.destroyAllWindows()                                # 화면에 나타난 윈도우 종료 
