# KTPS-Kursovaya

function varargout = untitled5(varargin)
gui_Singleton = 1;
gui_State = struct('gui_Name',       mfilename, ...
                   'gui_Singleton',  gui_Singleton, ...
                   'gui_OpeningFcn', @untitled5_OpeningFcn, ...
                   'gui_OutputFcn',  @untitled5_OutputFcn, ...
                   'gui_LayoutFcn',  [] , ...
                   'gui_Callback',   []);
if nargin && ischar(varargin{1})
    gui_State.gui_Callback = str2func(varargin{1});
end

if nargout
    [varargout{1:nargout}] = gui_mainfcn(gui_State, varargin{:});
else
    gui_mainfcn(gui_State, varargin{:});
end
end


function untitled5_OpeningFcn(hObject, eventdata, handles, varargin)
handles.output = hObject;
guidata(hObject, handles);
end

function varargout = untitled5_OutputFcn(hObject, eventdata, handles) 
varargout{1} = handles.output;
end


function edit1_Callback(hObject, eventdata, handles)
end

function edit1_CreateFcn(hObject, eventdata, handles)
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end


function edit2_Callback(hObject, eventdata, handles)
end
    
function edit2_CreateFcn(hObject, eventdata, handles)
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end


function edit3_Callback(hObject, eventdata, handles)
end

function edit3_CreateFcn(hObject, eventdata, handles)

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end

function edit4_Callback(hObject, eventdata, handles)
end

function edit4_CreateFcn(hObject, eventdata, handles)
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end

function pushbutton1_Callback(hObject, eventdata, handles)
    
a = get(handles.edit2,'string');
a = str2double(a);
b = get(handles.edit1,'string');
b = str2double(b);
sh = get(handles.edit3,'string');
sh = str2double(sh);
X =(a:sh:b);
formula = get(handles.edit4, 'String')
[x2,y2] = fplot(formula, [a b]);
KI = round(length(X)/length(x2));
x2 = interp(x2,KI);
y2 = interp(y2,KI);
ymax = max(y2);
ymin = min(y2);
plot(x2,y2,'LineWidth',3);
axis([a b ymin ymax])
end

function edit5_Callback(hObject, eventdata, handles)
end

function edit5_CreateFcn(hObject, eventdata, handles)
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end

function edit6_Callback(hObject, eventdata, handles)
end

function edit6_CreateFcn(hObject, eventdata, handles)
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end
end

function pushbutton2_Callback(hObject, eventdata, handles)
a = get(handles.edit2,'string');
a = str2double(a);
b = get(handles.edit1,'string');
b = str2double(b);
f = get(handles.edit6,'string');
f = str2double(f);
g = get(handles.edit5,'string');
g = str2double(g);
sh = get(handles.edit3,'string');
sh = str2double(sh);
X = a:sh:b;
x1 = 1:length(X);
a1 = abs(f-a)/sh;
b1 = abs(b-g)/sh;
formula = get(handles.edit4, 'String');
[x2,y2] = fplot(formula, [f g]);
KI = round(length(X)/length(x2));
x2 = interp(x2,KI);
y2 = interp(y2,KI);
plot(x2,y2,'LineWidth',3);
eks = max(y2);
set(handles.uitable1,'data',eks);
end
function pushbutton3_Callback(hObject, eventdata, handles)
a = get(handles.edit2,'string');
a = str2double(a);
b = get(handles.edit1,'string');
b = str2double(b);
f = get(handles.edit6,'string');
f = str2double(f);
g = get(handles.edit5,'string');
g = str2double(g);
sh = get(handles.edit3,'string');
sh = str2double(sh);
X = a:sh:b;
x1 = 1:length(X);
a1 = abs(f-a)/sh;
b1 = abs(b-g)/sh;
formula = get(handles.edit4, 'String');
[x2,y2] = fplot(formula, [f g]);
KI = round(length(X)/length(x2));
x2 = interp(x2,KI);
y2 = interp(y2,KI);
plot(x2,y2,'LineWidth',3);
eks = min(y2);
set(handles.uitable1,'data',eks);
end
